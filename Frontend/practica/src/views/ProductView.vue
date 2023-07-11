<template>
    <div class="container">
        <ProductoVenta>
            <template v-slot:producto v-bind="vendido">{{ vendido.nombre }}</template>
            <template v-slot:imagen1>
                <img :src="vendido.imagen" style="width:100%;" />
            </template>
            <template v-slot:descripcion1>
                <h6>
                    {{ vendido.descripcion }}
                </h6>
                <div class="p-3 mb-2 text-white" :style="configuracionPagina.precioEstilos">
                    Precio: {{ vendido.precio }} BOB
                </div>
            </template>
            <template v-slot:colores1>
                <div class="color-box" v-for="col in vendido.colores">
                    <div class="color-box clic" v-on:click="pedido.color = col"
                        :style="{ backgroundColor: active ? col : 'green' }">
                    </div>
                </div>
            </template>
            <template v-slot:colorSelec>
                <h5>Color seleccionado: {{ pedido.color }}</h5>
            </template>
            <template v-slot:botonesCompra>
                <div class="quantity">
                    <button v-on:click="pedido.cantidad -= 1" :disabled="pedido.cantidad <= 0">
                        -
                    </button>
                    <div>{{ pedido.cantidad }}</div>
                    <button v-on:click="pedido.cantidad += 1">+</button>
                </div>
                <div class="buy-box">
                    <button type="button" class="btn btn-primary" :disabled="pedido.cantidad <= 0"
                        v-on:click="comprarAlgo()">
                        Comprar
                    </button>
                </div>
            </template>
        </ProductoVenta>
    </div>
    <div class="container">
        <ProductRelacionado>
            <template v-slot:relacionado>
                <div class="col" v-for="item in items">
                    <div class="card" style="width: 18rem">
                        <div class="card-body">
                            <h5 class="card-title">{{ item.nombre }}</h5>
                            <img :src="item.imagen" alt="" style="width: 100%"/>
                            <p class="card-text">{{ item.descripcion }}</p>
                            <div class="producto-relacionado-precio">
                                Precio: {{ item.precio }} BOB
                            </div>
                            <div class="row">
                                <div class="color-box" v-for="colors in item.colores">
                                    <div class="color-box" :style="{ background: colors }"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </template>
        </ProductRelacionado>
    </div>
    <FooterProduct :style="{ backgroundColor: configuracionPagina.footerColor }">
        <template v-slot:comunicarse>
            <h5 style="color:white">
                Comuniquese con nosotros:
                <a href="#" style="color: red">
                   <u>Megadron@gmail.com</u></a>
            </h5>
        </template>
    </FooterProduct>
</template>
<style>
.color-box {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin: 7px;
    display: inline-block;
}

.clic {
    cursor: pointer;
}

.quantity button {
    border-radius: 50%;
    display: inline-block;
    width: 30px;
}

.quantity div {
    text-align: center;
    min-width: 30px;
    display: inline-block;
    font-weight: bold;
}

.buy-box {
    margin: 20px;
}

footer {
    text-align: center;
    padding: 30px 10px;
    margin-top: 50px;
    min-height: 100px;
}

.container {
    margin-top: 50px;
}

.producto-relacionado-precio {
    background: orangered;
    color: white;
    text-align: center;
    padding: 10px;
}
</style>
    
<script>
import ProductoVenta from '@/components/Producto.vue'
import ProductRelacionado from '@/components/Relacionados.vue'
import FooterProduct from '@/components/Footer.vue'
export default {
    name: 'Products',
    components: {
        ProductoVenta,
        ProductRelacionado,
        FooterProduct
    },
    data() {
        const appName = process.env.VUE_APP_NAME
        const api = process.env.VUE_APP_API
        return {
            api,
            items: [],
            primero: [],
            vendido: {},
            relacionado: [],
            configuracionPagina: {
                footerColor: "slategrey",
                precioEstilos:
                    "background: orangered; color: white; font-weight: bold",
            },
            active: true,
            pedido: {
                id: null,
                cantidad: 0,
                color: null
            }
        }
    },
    methods: {
        getProducts() {
            this.axios({
                method: "get",
                url: this.api + '/products'
            }).then((response) => {
                this.items = response.data;
                this.vendido = this.items[0];
                this.items.shift()
                console.log(this.items);
            }).catch((error) => {
                console.log(error);
            }).finally(() => { })
        }, comprarAlgo() {
            if (this.pedido.color != null) {
                this.pedido.id = this.vendido.id
                alert('Producto: ' + this.pedido.id + '\nCantidad: ' + this.pedido.cantidad +
                    '\nColor seleccionado: ' + this.pedido.color)

            }
        }
    },
    mounted() {
        this.getProducts();
    }
}
</script>