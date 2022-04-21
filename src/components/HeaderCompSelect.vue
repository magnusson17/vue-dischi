<template>
    <div>
      <select 
        name="select_genre" 
        id="select_genre" 
        class="p-2" 
        @click="$emit('funzioneGenere', valueGenere)">
        <option value="" disabled selected>Scegli un genere</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
</template>

<script>
export default {
    name: 'HeaderCompSelect',
}
</script>

<style scoped lang="scss">

</style>
