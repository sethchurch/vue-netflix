<template>

<nav class="navigation">

    <span class="navigation__links">
        <img src="../assets/logo.svg" class="navigation__logo" alt="logo">

        <h3 class="navigation__browse">Browse</h3>
    </span>

    <span class="search-container">
        <input type="text" class="search-container__input">
        <button class="search-container__submit">Search</button>
    </span>


    <div class="user-container">
        <img src="../assets/profile-image.jpg" class="user-container__image">
        <h5 class="user-container__user">{{ user }}</h5>
        
    </div>
</nav>

</template>

<script>

export default {
    name: 'navbar',
    props: ['user']
}

</script>

<style lang="scss">
    @import "../assets/_scss/navbar"
</style>