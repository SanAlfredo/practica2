<template>
  <div class="about">
    <div class="img-conteiner" align="center">
      <img :src="logo" alt="" width="800" />
    </div>
    <h1 class="textos">{{ appName }}</h1>
    <p class="listas"><i>La empresa nace como una sociedad anónima, con el capital de 4 compañeros empresarios privados que nos conocimos
        dentro de la Universidad.</i></p>
    <div class="row" v-for="(item, key) in acerca">
      <h3 class="textos">{{ key }}</h3>
      <p class="listas"><i>{{ item }}</i> </p>
    </div>
  </div>
</template>
<script>

export default {
  name: 'About',
  data() {
    const appName = process.env.VUE_APP_NAME
    return {
      appName,
      logo: "https://blog.advesa.com/wp-content/uploads/2019/11/about-us-page.png",
      acerca:
      {
        objetivo: "El objetivo de la empresa es de incorporar nuevos modelos de drones importados desde el extranjero",
        mision: "Brindar la mejor atención posible y la ayuda a los clientes con productos de calidad",
        vision: "Esperamos a futuro poder expandirnos y contar con sucursales en más departamentos."
      }

    }
  }
}
</script>