<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Página dedicada a la venta de drones para todo uso, de todos los colores.
    </p>
    <h3>Visitanos</h3>
    <ul v-for="item in visita">
      <li>{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data (){
    return {
      visita:['La Paz','Cochabamba','Santa Cruz']
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
