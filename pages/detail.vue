<template>
  <main>
    
    <DetailHeader/>
    <DetailDescritpion/>
  </main>
</template>

<script setup>
    import DetailDescritpion from '~~/components/Detail/DetailDescritpion.vue';
    import DetailHeader from '../components/Detail/DetailHeader.vue';
</script>

<style scoped>
    main{
        min-height: 100vh;
        background-color: #B8B8B8;
        padding: 4px;
    }

    @media screen and (min-width: 600px) {
        main{
            padding: 12px 25px;
        }
    }
</style>
