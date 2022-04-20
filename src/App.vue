<template>
  <div>
    <HeaderComp/>
  </div>
</template>

<script>
import "bootstrap"

import HeaderComp from './components/HeaderComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

</style>
