<template>
  <div class="p-3 d-flex justify-content-between align-items-center">
    <div class="">
      <img src="../assets/img/logo.svg" alt="">
    </div>

    <div>
      <select name="select_genre" id="select_genre" class="p-2">
        <option value="" disabled selected>Scegli un genere</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
    name: 'HeaderComp',
}
</script>

<style scoped lang="scss">
div {
    background-color: #2E3A46;
    img {
        height: 50px;
    }
}
</style>
