<template>
  <div id="app">
      

    <div class="catagories">

      <Category title="Trending" api-options=""></Category>

      <Category title="Action Films" api-options="&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=28"></Category>

      <Category title="Comedies" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=35"></Category>

      <Category title="Animated Films" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=16"></Category>
    
    </div>
  </div>
</template>

<script>
    import Category from './components/Category'

    export default {
        name: 'app',
        components: {
            Category
        }
    }
</script>

<style lang='scss'>
    @import './assets/_scss/main.scss';
</style>