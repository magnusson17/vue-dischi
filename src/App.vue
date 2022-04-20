<template>
  <div>
    <HeaderComp/>
    <MainComp/>
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

</style>
