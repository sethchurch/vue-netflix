<template>
<div class="hello">

    <ul>

        <li v-for="movie in movie_data.value.results" >
            {{ name }}
            <img v-bind:src="getImageUrl(movie.backdrop_path)">
                <h2> {{ movie.original_title }} </h2>
                <p> IMDb Rating: {{ movie.vote_average }}/10 </p>
            </img>
        </li>


    </ul>

</div>
</template>

<script>
    export default {
        name: 'hello',
        props: ['name'],
        data() {
            return {
                movie_data: {}
            }
        },
        methods: {
            getImageUrl(url) {
                return "http://image.tmdb.org/t/p/w185/" + url;
            }
        },
        fetch: {
            movie_data: () => "https://api.themoviedb.org/3/discover/movie?api_key=cbd6aed8ebb901c0305b2e761eb59974"
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1,
    h2 {
        font-weight: normal;
    }
    
    ul {
        list-style-type: none;
        padding: 0;
        display: flex;
        flex-wrap: wrap;
    }
    
    li {
        margin: 10px;
        height: 500px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    
    li h2 {
        width: 200px;
        height: 80px;
    }
</style>