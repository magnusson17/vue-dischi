<template>
  <div id="MainComp_div" class="row row-cols-6 justify-content-center">
      <!-- 6) non faccio più il v-for su salvoArrayAxios MA lo faccio su funFiltraggio -->
    <MainCompSon
        v-for="(element, index) in funFiltraggio"
        :key="index"
        :poster="element.poster"
        :title="element.title"
        :author="element.author"
        :year="element.year"
    />
  </div>
</template>

<script>
import axios from 'axios';
import MainCompSon from './MainCompSon.vue';

export default {
    name: 'MainComp',
    components: {
        MainCompSon,
    },
    // 4) passo i promps
    props: {
        propsPassoGeneriAFirstSon: String,
    },

    data() {
        return {
            // 1) salvo, con axios, l'api dentro un mio array
            salvoArrayAxios: [],
            // 2) questo array dovro farlo girare da son1 a dad a son2 (qua farò riferimento qundo scelgo un value della select)
            salvoGeneri: []
        }
    },
    
    // 5) ora che ho i promps (quindi ho finalmente il value che è partito da son2) faccio il filtraggio
    computed: {
        funFiltraggio() {
            if (this.propsPassoGeneriAFirstSon === '') {
            return this.salvoArrayAxios
            } else {
                return this.salvoArrayAxios.filter((el) => {
                    return el.genre.includes(this.propsPassoGeneriAFirstSon);
                })
            }
        }   
    },

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (res) => {
            console.log(res.data);
            // 1) salvo, con axios, l'api dentro un mio array
            this.salvoArrayAxios = res.data.response;

            // 2) riempio l'array generi
            this.salvoArrayAxios.forEach(el => {
                if (!this.salvoGeneri.includes(el.genre)) {
                    this.salvoGeneri.push(el.genre)
                }
            });

            // 3) ora sposto da son1 a dad l'array coi generi ('spostoGeneriSonToDad' è una fun, this.salvoGeneri è il paramentro) -> ora passo al dad (app.vue)
            this.$emit('spostoGeneriSonToDad', this.salvoGeneri)
        })
        .catch( (error) => {
           console.log( error )
         } )
    }
}
</script>

<style scoped lang="scss">
.MainComp_div {
    width: 90%;
}
</style>