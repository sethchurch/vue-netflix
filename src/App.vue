<template>
  <div id="app">
    <Navbar user="seth" />

    <Header/>

    <section class="categories">

      <Category title="Trending" api-options="" />

      <Category title="Action Films" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=28" />

      <Category title="Comedies" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=35" />

      <Category title="Animated Films" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=16" />
    
      <Category title="Science Fiction Films" api-options="language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=878" />
    </section>

  </div>
</template>

<script>
    import Header from './components/Header'
    import Category from './components/Category'
    import Navbar from './components/Navbar'

    export default {
        name: 'app',
        components: {
            Header,
            Category,
            Navbar
        }
    }
</script>

<style lang='scss'>
    @import './assets/_scss/main.scss';
</style>