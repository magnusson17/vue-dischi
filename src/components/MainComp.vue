<template>
  <div>
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
import MainCompSon from './MainCompSon.vue';

export default {
    name: 'MainComp',
    components: {
        MainCompSon,
    },

    data() {
        return {
            salvoArrayAxios: [],
        }
    },

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (response) => {
            console.log(response.data);
            this.salvoArrayAxios = response.data;
        })
        .catch( (error) => {
           console.log( error )
         } )
    }
}
</script>

<style scoped lang="scss">

</style>