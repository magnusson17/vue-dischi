<template>
  <div>
    main
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'MainComp',

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