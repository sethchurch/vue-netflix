<template>

    <div class="filmCard">

    <img :src="getImageUrl(show.backdrop_path)" :alt="show.original_title"> 



    <span class="content">
            <button v-on:click="toggleFavorited" :class="{ favorited: isFavorited }">

                <span v-if="isFavorited"> - </span>
                <span v-else> + </span>

            </button>

            <span class="show-desc">
                <h3 :class="{ smaller: show.original_title.length > 20 }"> {{ show.original_title }} </h3>
                <p> {{ show.vote_average }}/10 </p>
                <p> {{ show.overview.length > 80 ? (show.overview.slice(0,80) + "...") : show.overview }} </p>
            </span>
            
       </span>
    </div>

</template>


<script>
    export default {
        name: 'filmCard',
        props: ['show'],
        data() {
            return {
                isFavorited: false
            }
        },
        methods: {
            getImageUrl(url) {
                return `http://image.tmdb.org/t/p/w300/${url}`;
            },
            toggleFavorited() {
                this.isFavorited = !this.isFavorited;
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/_scss/filmcard.scss';
</style>