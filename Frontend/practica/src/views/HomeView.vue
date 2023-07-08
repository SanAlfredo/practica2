<template>
  <div class="home">
    <img alt="Vue logo" :src="logo" width="600">
    <HelloWorld msg="Bienvenidos a MegaDron"/>
  </div>
</template>

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
