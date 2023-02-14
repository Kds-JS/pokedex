<template>
    <Head>
        <Title>Pokemon Collection </Title>
        <Meta name="description" content="Pokemon Collection"/>
    </Head>
  <main>
    <HomeHeader :inputValue="inputValue" :onInput="onInput" :clearInputValue="clearInputValue"/>
    <PokedexList :pokemons="pokemons"/>
  </main>
</template>

<script setup>
    import HomeHeader from '../components/Home/HomeHeader.vue';
    import PokedexList from '../components/Home/PokedexList.vue';
    import { ref, computed } from 'vue';

    const inputValue = ref('');
    const data = ref({});
    const array = ref([]);
    const pokemons = ref([]);

    function onInput(e) {
        inputValue.value = e.target.value;
        console.log(inputValue.value);
    }

    function clearInputValue() {
        inputValue.value = ''
    }

   

    watchEffect(() => {
            if(inputValue.value.trim().length > 0) {
                pokemons.value = array.value.filter(pokemon => pokemon.name.toLowerCase().includes(inputValue.value.toLowerCase().trim()));
            } else {
                pokemons.value = array.value;
            }

            console.log(pokemons.value);
    })

    async function fetchData() {
        const res = await fetch(
            'https://pokeapi.co/api/v2/pokemon?limit=70'
        )
        data.value = await res.json();
    }

    onMounted(() => {
        fetchData();
    })


    watchEffect(() => {
        data.value.results?.forEach(async (element) => {
        const {data: pokemon} = await useFetch(`https://pokeapi.co/api/v2/pokemon/${element.name}`);
        array.value.push(pokemon.value);
      })
    });

   
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
