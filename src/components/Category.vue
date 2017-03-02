<template>
 <div class="category" >
     <h1> {{ title }} </h1>
     <div class="category__show-list">
        <FilmCard 
        class="film-card"
        v-for="movie in category_data.value.results.slice(0,6)" 
        :show="movie"
        :key="movie.id"
        ></FilmCard>
     </div>
 </div>
</template>

<script>
    import FilmCard from './filmCard';

    export default {
        name: 'category',
        components: {
            FilmCard
        },
        props: ['title', 'apiOptions'],
        data() {
            return {
                category_data: {}
            }
        },
        fetch: {
            category_data: vue => {
                return "https://api.themoviedb.org/3/discover/movie?api_key=cbd6aed8ebb901c0305b2e761eb59974&" + vue.apiOptions || ""
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '../assets/_scss/category'
</style>