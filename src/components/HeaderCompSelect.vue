<template>
    <div>
      <select 
        name="select_genre" 
        id="select_genre" 
        class="p-2" 
        v-model="valoreFromSelect"
        @click="$emit('funValoreFromSelect', valoreFromSelect)">
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

    data() {
        return {
            valoreFromSelect: '',
        }
    }
}
</script>

<style scoped lang="scss">

</style>

questi due componenti sono "fratelli"
16:36
ed hanno in comune un "padre" che è App.vue
16:37
in questo caso il passaggio che devi fare è, passare il genere scelto da HeaderCompSelect al padre (app.vue) e successivamente da App.vue al figlio MainComp con le props.





16:38
il metodo corretto è creare una funzione dentro ad app.vue
16:38
e passare questa funzione a HeaderCompSelect con le prop che avete visto stamattina
16:38
<componente @startSearch="myFunction">
16:38
la funzione deve prevedere di avere un parametro
16:39
e dentro HeaderCompSelect, al change della select dovrai fare l'emit di quella funzione (ricevuta da app.vue)
