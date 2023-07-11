<template>
    <div class="row">
        <h4>Productos relacionados</h4>
    </div>
    <div class="row">
        <slot name="relacionado"></slot>
        
    </div>
</template>
  
<script>
export default {
    name: 'ProductRelacionado',
    data() {
    }
}
</script>