<template>
  <div class="home">
    <div align="center">
      <img alt="Vue logo" :src="logo" width="600">
    </div>
    <HelloWorld msg="Bienvenidos a MegaDron"/>
  </div>
</template>
<style type="text/css">
.textos {
  text-align: center;
  color:midnightblue
}
.listas {
  text-align:center;
  color: darkgreen;
  font-size: large;
}
</style>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data (){
    return {
      logo:"https://img.freepik.com/fotos-premium/drones-sociedad-futuro_825081-537.jpg?w=2000"
    }
  }
}
</script>
