<template>
        <div class="container">
          <div class="row">
            <div class="col-12">
               <Card v-for="(element, index) in pellicole" :key="index" :movie="element"/>

              <!--  <Card v-for="element in tvSeries" :key="element.id" :movie="element"/>-->
            </div>
          </div>
        </div>
</template>

<script>
//import axios from 'axios';
import Card from './Card.vue';

export default {
  name: 'Main',
  props: {
    pellicole : Array,
    tvSeries : Array
  },

  components: {
   Card,
  },

  data : function () {
    return {
   
    }
  },

    methods: {
    
      
    
  },

  
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
 


</style>

<!--

    updated : function () {

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=cb11640258dfdce63e5b0a147809a751'.concat('&query=').concat(this.research.toString()))
    .then(res => {
      
      //console.log(res.data.results[0].title)

      for (let i=0; i<res.data.results.length; i++) {

        this.chunk.title = res.data.results[i].title;
        this.chunk.original_title = res.data.results[i].original_title;
        this.chunk.original_language = res.data.results[i].original_language;
        this.chunk.vote_average = res.data.results[i].vote_average;

        this.titleArr.push(res.data.results[i].title, res.data.results[i].original_title,
        res.data.results[i].original_language, res.data.results[i].vote_average)
        
      
        console.log(this.chunk)
      }

      console.log(typeof(this.chunk)) //object
   
      /*
      while (this.titleArr.length > 0) {

      this.chunk = this.titleArr.splice(0,4)

}

    */


      //console.log(this.titleArr)
      
      //res.data.results.forEach(element => {
      
      //this.titleArr.push(element.title, element.original_title, element.original_language, element.vote_average)
     
      //console.log(this.titleArr)
      }

      
  
    )//});
 
  }-->


