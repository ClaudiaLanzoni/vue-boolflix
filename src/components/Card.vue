<template>
    
    <div class="card_box">

        <div class="movie_img">
            <img v-if="movie.poster_path" :src="imgPercorso+movie.poster_path" alt="research image">
            <img v-else-if="movie.poster_path == null" src="../assets/boolflix_placeholder.png" alt="research image">
        </div>
            

        <div class="info_movie_container">

            <div><span class="fw-bold">Titolo: </span>{{movie.title ? movie.title : movie.name}}</div>
            <div><span class="fw-bold">Titolo originale: </span>{{movie.original_title ? movie.original_title : movie.original_name}}</div>

            <img v-if="movie.original_language == 'en'" src="../assets/uk_flag.png" alt="Uk flag">
            <img v-else-if="movie.original_language == 'it'" src="../assets/italy_flag.png" alt="Italian flag">
            <div v-else>{{movie.original_language}}</div>

            <div class="text-white"><span class="fw-bold">Voto: </span>
                <span v-for="n in starGenerator(movie.vote_average)" :key="n">&starf;</span>
                <span v-for="n in 5 - starGenerator(movie.vote_average)" :key="n">&star;</span></div>
            <!--<span>{{ movie.vote_average != 5 ? starMultiplier() : '' }}</span>-->

            <!--<div><span class="fw-bold">Voto: </span>{{movie.vote_average}}</div>-->

            <div><span class="fw-bold">Overview :</span>{{movie.overview}}</div>

        </div>
        
    </div>

  
</template>

<script>
export default {
    name : 'Card',
    props : ['movie'],
    data : function () {
        return {
            imgPercorso : 'https://image.tmdb.org/t/p/w342'
        }
    
    },
    methods : {
        starGenerator (vote) {
            return Math.ceil(vote)/2
        },
    }
}
</script>

<style scoped lang='scss'>

    .card_box {
        border: 3px solid white;
        height: 465px;
        width: 350px;
        font-size: 12px;
    }

    .movie_img {
        height: 458px;
        width: 342px;
        display: block;
        
            &:hover {
                display: none;
            }
    }

    .info_movie_container {
        height: 458px;
        width: 342px;
        background-color: black;
        color: white;
        padding: 20px;

            &:hover {
                display: block;
            }
    }
    
    

</style>