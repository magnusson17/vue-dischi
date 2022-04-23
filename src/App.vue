<template>
  <div id="first_div">
    <div id="header" class="p-3 d-flex justify-content-between align-items-center">
      <HeaderComp/>
      <!-- 3) ora devo passare al son2, quindi faccio un promp: propsPassoGeneriASecondSon è il nome del promp, generi è il dato che voglio passare. Quindi ora vado sul son2 (HeaderCompSelect.vue)  -->

      <!-- 4) ricevo l'emit funValoreFromSelect da son2 e, da quello, creo un metodo proprio del dad: funSelectMetodoPadre -->
      <HeaderCompSelect 
        :propsPassoGeneriASecondSon="generi"
        @funValoreFromSelect="funSelectMetodoPadre"/>
    </div>
    <div class="container d-flex justify-content-center py-5">
      <!-- 1) richiamo la fun che ho creato in son1 con l'emit e la trasformo in una nuova fun questa volta "prorpria" del dad, che sara usata appunto nei methods del dad -->

      <!-- 5) ora passo valoreSalvatoInPadre a son1 con un props, quindi vado in son1 (MainComp.vue) -->
      <MainComp
        @spostoGeneriSonToDad="lavoroGeneriInDadFun"
        :propsPassoGeneriAFirstSon="valoreSalvatoInPadre"/>
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
      // 4)
      valoreSalvatoInPadre: '',
      // 2) creo un array proprio del dad per contenere i generi
      generi: []
    }
  },

  methods: {
    // 2) salvo i generi dall'array di son1 nel array di dad(il paramentro di questa fun fa riferimento al dato this.salvoGeneri in son1)
    lavoroGeneriInDadFun(thisSalvoGeneri) {
      // in pratica gli dico: generi[] (del dad) = generi[] (del son)
      this.generi = thisSalvoGeneri;
    },

    // 4)
    funSelectMetodoPadre(valoreFromSelect) {
      this.valoreSalvatoInPadre = valoreFromSelect
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
