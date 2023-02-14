<template>
    <Head>
        <Title>Pokemon || {{ pokemon.name }} </Title>
        <Meta name="description" :content="pokemon.name"/>
    </Head>
    <main :style="{backgroundColor:  color[pokemon.types[0].type.name]}">
      
      <DetailHeader :pokemon="pokemon"/>
      
      <DetailDescritpion :pokemon="pokemon"/>
    </main>
  </template>
  
  <script setup>
      import DetailDescritpion from '~~/components/Detail/DetailDescritpion.vue';
      import DetailHeader from '~~/components/Detail/DetailHeader.vue';
      import {color} from '../../utils/color';

    const {id} = useRoute().params;
    const uri = 'https://pokeapi.co/api/v2/pokemon/' + id;
    // fetch the pokemon
    const {data: pokemon} = await useFetch(uri);
  
    // console.log(pokemon);

    if(!pokemon.value) {
        throw createError({statusCode: 404, statusMessage: 'Product not found', fatal: true})
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
  