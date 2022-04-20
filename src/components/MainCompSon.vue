<template>
  <div>
    <img :src="poster" alt="" class="">
    <h3>{{title}}</h3>
    <h6>{{author}}</h6>
    <h6>{{year}}</h6>
  </div>
</template>

<script>
export default {
    name: 'MainCompSon',
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
    },
}
</script>

<style scoped lang="scss">

</style>