<template>
    <div>
      <!-- 3.1) con v.model salvo il value delle option dentro un data, che farà da contenitore, che creo io  -->
      <!-- 3.2) al click creo un emit che passerò al dad ('funValoreFromSelect' è la fun, valoreFromSelect è il data contenitore dentro il quale ho salvato il value), ora torno sul dad -->
      <select 
        v-model="valoreFromSelect"
        @change="$emit('funValoreFromSelect', valoreFromSelect)"
        name="select_genre" 
        id="select_genre" 
        class="p-2">
        <option value="" disabled selected>Scegli un genere</option>
        <option value="">Tutti i generi</option>
        <!-- 2) ciclo l'array che contiene i props (ogni element contiene un genere) -->
        <option 
          v-for="(element, index) in propsPassoGeneriASecondSon" 
          :key="index"
          :value="element">{{element}}
        </option>
      </select>
    </div>
</template>

<script>
export default {
    name: 'HeaderCompSelect',
    // 1) devo inserire i promps che mi arrivano dal dad
    props: {
      propsPassoGeneriASecondSon: Array,
    },

    data() {
        return {
          // 3.1) salvo il value selezionato dentro un mio data
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
