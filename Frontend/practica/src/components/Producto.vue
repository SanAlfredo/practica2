<template>
    <div class="row">
        <div class="col s12 m6 l4">
            <h5>
                <slot name="producto"></slot>
            </h5>
            <slot name="imagen1"></slot>
        </div>
        <div class="col s12 m6 l8">
            <slot name="descripcion1"></slot>
            <h5>Color</h5>
            <div class="row">
                <slot name="colores1"></slot>
            </div>
            <div class="col">
                <div>
                    <slot name="colorSelec"></slot>
                    
                    <h5>Cantidad</h5>
                </div>
                <slot name="botonesCompra"></slot>
                
            </div>

        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductoVenta',
    data() {
        return {
            
        }
    }
}
</script>