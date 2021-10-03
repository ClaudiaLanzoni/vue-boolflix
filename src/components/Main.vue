<template>
    <div>
      <input type="text" placeholder="Cerca un titolo" v-model="research">
      <button>Inizia ricerca</button>
      <div class="ul_box">

          <ul >
            <li v-for="element, index in chunk" :key="index">
              {{element}}
            </li>
          </ul>

                 <!--Titolo title
                  Titolo Originale original_title
                  Lingua original_language
                  Voto vote_average-->
      </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Main',
  props: {
    
  },

  data : function () {
    return {
      titleArr : [],
      chunk : [],
      uniqueMovies : [],
      research : ''
    }
  },

  computed: {
    filterMovie: function(){
          
          return this.chunk.filter((input) => { 
              //if (this.titleArr.indexOf(input) > -1) {
                return input.includes(this.research);
              //}
          
          });

          
      }       
    },
   

    updated : function () {

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=cb11640258dfdce63e5b0a147809a751'.concat('&query=').concat(this.research.toString()))
    .then(res => {
      
      //console.log(res.data.results[0].title)

      for (let i=0; i<res.data.results.length; i++) {
        this.titleArr.push(res.data.results[i].title, res.data.results[i].original_title,
         res.data.results[i].original_language, res.data.results[i].vote_average)
      }

      while (this.titleArr.length > 0) {

      this.chunk = this.titleArr.splice(0,4)

}

    


      //console.log(this.titleArr)
      
      //res.data.results.forEach(element => {
      
      //this.titleArr.push(element.title, element.original_title, element.original_language, element.vote_average)
     
      //console.log(this.titleArr)
      }

      
  
    )//});
 
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
 
  .ul_box {
    border: 3px solid black;
  }


</style>
