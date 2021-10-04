<template>
    <div class="movie_box">
        <div>{{movie.title ? movie.title : movie.name}}</div>
        <div>{{movie.original_title ? movie.original_title : movie.original_name}}</div>

        <img v-if="movie.original_language == 'en'" src="../assets/uk_flag.png" alt="Uk flag">
        <img v-else-if="movie.original_language == 'it'" src="../assets/italy_flag.png" alt="Italian flag">
        <div v-else>{{movie.original_language}}</div>

        <div>{{movie.vote_average}}</div>
    </div>
</template>

<script>
export default {
    name : 'Card',
    props : ['movie']
}
</script>

<style scoped lang='scss'>

    .movie_box {
        border: 2px solid black;
        margin: 5px;
    }

</style>