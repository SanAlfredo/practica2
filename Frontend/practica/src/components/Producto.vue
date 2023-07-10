<template>
    <div class="row">
        <h3>Nombre del producto</h3>
    </div>
    <div class="row">
        <div class="col">
            <div class="col">
                <img src="https://www.cu-reduceri.ro/images/vouchers/4922/1414.png" alt="" width="325" />
            </div>
        </div>
        <div class="col">
            <div class="row">
                <div class="col">
                    <h6>Descripcion del producto</h6>
                    <div class="p-3 mb-2 text-white" style="background-color: orangered;">
                        Precio: 500 BOB
                    </div>
                    <h5>Color</h5>
                    <div class="row">
                        <div class="color-box">
                            <div class="color-box clic" style="background-color: red"></div>
                        </div>
                    </div>
                    <div class="col">
                        <div>
                            <h5>Color Seleccionado color</h5>
                            <h5>Cantidad</h5>
                        </div>
                        <div class="quantity">
                            <button>
                                -
                            </button>
                            <div>0</div>
                            <button>+</button>
                        </div>
                        <div class="buy-box">
                            <button type="button" class="btn btn-primary">
                                Comprar
                            </button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'ProductoVenta',
    data() {
    }
}
</script>