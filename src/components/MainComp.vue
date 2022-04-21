<template>
  <div id="MainComp_div" class="row row-cols-6 justify-content-center">
    <HeaderCompSelect @funzioneGenere="metodoTrovaGenere"/>

    <MainCompSon
        v-for="(element, index) in salvoArrayAxios"
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
import HeaderCompSelect from './HeaderCompSelect.vue';
import MainCompSon from './MainCompSon.vue';

export default {
    name: 'MainComp',
    components: {
        HeaderCompSelect,
        MainCompSon,
    },

    data() {
        return {
            salvoArrayAxios: [],
        }
    },

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (res) => {
            console.log(res.data);
            this.salvoArrayAxios = res.data.response;
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