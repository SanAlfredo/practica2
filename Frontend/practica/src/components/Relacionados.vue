<template>
    <div class="row">
        <h4>Productos relacionados</h4>
    </div>
    <div class="row">
        <div class="col">
            <div class="card" style="width: 18rem">
                <div class="card-body">
                    <h5 class="card-title">Nombre producto</h5>
                    <img src="https://www.cu-reduceri.ro/images/vouchers/4922/1414.png" alt="" width="100%" />
                    <p class="card-text">descripcion</p>
                    <div class="producto-relacionado-precio">
                        Precio: 100 BOB
                    </div>
                    <div class="row">
                        <div class="color-box">
                            <div class="color-box" style="background-color: red"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'ProductRelacionado',
    data() {
    }
}
</script>