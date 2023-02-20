<template>
    <Head>
        <Title>Pokemon || {{ pokemon.name }} </Title>
        <Meta name="description" :content="pokemon.name"/>
    </Head>
    <main :style="{backgroundColor:  color[pokemon.types[0].type.name]}">
      
      <DetailHeader :pokemon="pokemon" :previewPokemon="previewPokemon" :nextPokemon="nextPokemon" />
      
      <DetailDescritpion :pokemon="pokemon"/>
    </main>
  </template>
  
  <script setup>
      import DetailDescritpion from '~~/components/Detail/DetailDescritpion.vue';
      import DetailHeader from '~~/components/Detail/DetailHeader.vue';
      import {color} from '../../utils/color';
      import {ref} from 'vue';

    let {id} = useRoute().params;
    const newId = ref(id);
    let uri = 'https://pokeapi.co/api/v2/pokemon/' + id;
    // fetch the pokemon
    let {data: pokemon} = await useFetch(uri);
  
    // console.log(pokemon);

    watch(newId, async () => {
        let uri = 'https://pokeapi.co/api/v2/pokemon/' + newId.value;
        const {data: newPokemon} = await useFetch(uri);
        pokemon = newPokemon;
        console.log(pokemon);
    })

    function nextPokemon() {
        newId.value++;
        console.log(newId.value);
    }

    function previewPokemon() {
        if(newId.value !== 1) {
            newId.value--;
        }
    }

    
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
  