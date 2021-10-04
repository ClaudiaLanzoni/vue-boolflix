<template>
  <div>
      <input type="text" placeholder="Cerca un titolo" v-model.trim="research" > 
        <button @click="$emit('searching', research)">Inizia ricerca</button> <!-- quando l'evento custom viene scatenato dalla emit
                                                                            viene chiamata la funzione search;
                                                                            si passa argomento 'research'-->
  </div>
</template>

<script>
export default {
    name : 'Header',
    props : {

    },

    data : function () {
    return {

      research : ''
    }
  },

}
</script>

<style>

</style>