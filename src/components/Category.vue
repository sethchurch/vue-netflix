<template>
 <div class="category" >
     <h1> {{ title }} </h1>
     <section class="show-container">

        <span v-on:mouseenter="scrollLeft(-1)" v-on:mouseleave="clearScroll"  class="show-container__control" />

        <div ref="scroller" class="category__show-list">
            <div class="transform-wrapper">
                <FilmCard 
                class="film-card"
                v-for="movie in category_data.value.results" 
                :show="movie"
                :key="movie.id"
                />
            </div>
        </div>

        <span v-on:mouseenter="scrollLeft(1)" v-on:mouseleave="clearScroll" class="show-container__control" />

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
            scrollLeft(amount) {
                this.scroll = setInterval(() => this.$refs.scroller.scrollLeft += amount, 5)
            },
            clearScroll() {
                clearInterval(this.scroll);
            }
        },
        fetch: {
            category_data: vue => {
                return "https://api.themoviedb.org/3/discover/movie?api_key=API_KEY&" + vue.apiOptions || ""
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '../assets/_scss/category'
</style>
