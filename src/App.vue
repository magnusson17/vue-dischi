<template>
  <div id="first_div">
    <HeaderComp/>
    <div class="container d-flex justify-content-center py-5">
      <MainComp/>
    </div>
  </div>
</template>

<script>
import "bootstrap"

import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

#first_div {
  background-color: #1E2D3B;
}

</style>
