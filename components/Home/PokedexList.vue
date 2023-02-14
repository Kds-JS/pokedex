<template>
  <section>
    <div class="container">
        <div v-for="pokemon in pokemons" :key="pokemon.id">
            <PokedexCard :pokemon="pokemon"/>
        </div>
    </div>

  </section>
</template>

<script setup>
    import PokedexCard from './PokedexCard.vue';
    const { pokemons} = defineProps(['pokemons'])
    // console.log(pokemons);
</script>

<style scoped>
    section{
        background-color: white;
        border-radius: 8px;
        padding: 24px 12px;
        min-height: 80vh;
    }

    .container{
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 8px;
    }

    @media screen and (min-width: 768px) {
        .container{
            grid-template-columns: repeat(5, 1fr);
            grid-gap: 14px;
        }
    }

    @media screen and (min-width: 992px) {
        .container{
            grid-template-columns: repeat(7, 1fr);
        }
    }

    @media screen and (min-width: 992px) {
        .container{
            grid-template-columns: repeat(8, 1fr);
        }
    }
</style>
