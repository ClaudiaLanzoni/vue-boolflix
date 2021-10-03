<template>
    <div class="movie_box">
        <div>{{movie}}</div>
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