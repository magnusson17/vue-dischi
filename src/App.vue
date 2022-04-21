<template>
  <div id="first_div">
    <div id="header" class="p-3 d-flex justify-content-between align-items-center">
      <HeaderComp/>
      <HeaderCompSelect @funValoreFromSelect="funFromMetodoPadre"/>
    </div>
    <div class="container d-flex justify-content-center py-5">
      <MainComp/>
    </div>
  </div>
</template>

<script>
import "bootstrap"

import HeaderComp from './components/HeaderComp.vue'
import HeaderCompSelect from './components/HeaderCompSelect.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    HeaderCompSelect,
    MainComp
  },

  data() {
    return {
      valoreSalvatoInPadre: ''
    }
  },

  computed: {
    funFiltraggio() {
      if (this.valoreSalvatoInPadre == '') {
        return this.salvoArrayAxios
      } else {
        return this.salvoArrayAxios.filter((item) => {
          return item.genre.toLowerCase().includes(this.valoreSalvatoInPadre.toLowerCase());
        })
      }
    }
  },

  methods: {
    funFromMetodoPadre(genere) {
      this.valoreSalvatoInPadre = genere;
    }
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

#first_div {
  background-color: #1E2D3B;
}

#header {
  background-color: #2E3A46;
}

</style>
