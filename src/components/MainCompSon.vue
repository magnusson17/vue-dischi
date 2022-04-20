<template>
  <div class="col p-2 m-2 text-white">
    <img :src="poster" alt="" class="img-thumbnail">
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
div {
    background-color: #2E3A46;
}
</style>