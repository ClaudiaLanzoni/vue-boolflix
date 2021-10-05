<template>
  <div class="header_wrap ">
    <div class="d-flex justify-content-end pt-3">
      <img class="logo_size" src="../assets/logo_filmzflix.png" alt="logo filmzflix">
      <input type="text" placeholder="Cerca un titolo" v-model.trim="research" class="mx-2"> 
      <button @click="$emit('searching', research)" type="button" class="btn btn-danger mx-2">Inizia ricerca</button> <!-- quando l'evento custom viene scatenato dalla emit
                                                                         viene chiamata la funzione search;
                                                                            si passa argomento 'research'-->
    </div>   
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

<style scoped lang="scss">
  .header_wrap {
    height: 70px;
    background-color: black;
  }

  .logo_size {
    height: 35px;
  }
</style>