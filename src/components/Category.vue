<template>
 <div class="category" >
     <h1> {{ title }} </h1>
     <section class="show-container">

        <span v-on:mouseenter="scrollRight" v-on:click="scrollRight"  class="show-container__control" />

        <div id="scroller-list" class="category__show-list">
            <div class="transform-wrapper">
                <FilmCard 
                class="film-card"
                v-for="movie in category_data.value.results" 
                :show="movie"
                :key="movie.id"
                />
            </div>
        </div>

        <span v-on:mouseenter="scrollLeft" v-on:click="scrollLeft" class="show-container__control" />

     </section>
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
        methods: {
            scrollLeft(e) {
                document.querySelector("#scroller-list").scrollLeft += 50;
            },
            scrollRight(e) {
                document.querySelector("#scroller-list").scrollLeft -= 50;
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