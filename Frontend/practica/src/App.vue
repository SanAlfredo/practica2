<template>
  <div class="container">
    <nav class="nav-extended" style="background-color: teal;">
      <div class="nav-wrapper">
        <a href="#" class="brand-logo">Megadron</a>
        <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
        <ul id="nav-mobile" class="right hide-on-med-and-down">
          <Menu></Menu>
        </ul>
      </div>
    </nav>

    <ul class="sidenav" id="mobile-demo" style="background-color: teal">
      <Menu></Menu>
    </ul>
    <router-view />
  </div>
</template>

<style lang="scss"></style>

<script>
import Menu from '@/components/Menu.vue'
export default {
  name: 'AppView',
  components: {
    Menu
  },
  data() {
    return {
    }
  },
  created() {
    document.addEventListener('DOMContentLoaded', function () {
      var elems = document.querySelectorAll('.sidenav');
      var instances = M.Sidenav.init(elems, {});
    });
  }
}
</script>
