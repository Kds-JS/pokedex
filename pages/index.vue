<template>
  <main>
    <Header/>
    <PokedexList />
  </main>
</template>

<script setup>
    import Header from '../components/Home/Header.vue';
    import PokedexList from '../components/Home/PokedexList.vue';

</script>

<style scoped>
    main{
        min-height: 100vh;
        background-color: #DC0A2D;
        padding: 4px;
    }

    @media screen and (min-width: 600px) {
        main{
            padding: 12px 25px;
        }
    }
    

</style>
