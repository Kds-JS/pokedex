<template>
  <section>
    <div class="title">
        <NuxtLink to="/">
            <Icon icon="ic:round-arrow-back"/>
        </NuxtLink>
        <h1>Pokémon name</h1>
        <span>#044</span>
    </div>

    <div class="item">

        <div class="icon">
            <Icon icon="material-symbols:chevron-left"/>
            <Icon icon="material-symbols:chevron-right"/>
        </div>

        <div class="image">
        <img src="../../assets/Silhouette.png" alt="image">
        </div>

    </div>

    <div class="pokeball">
        <img src="../../assets/BigPokeball.png" alt="pokeball">
    </div>

   
  </section>
</template>

<script setup>
    import { Icon } from '@iconify/vue';
</script>

<style scoped>

    section{
        position: relative;
    }
    .title{
        padding: 20px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 8px;
        color: white;
    }

    .title svg{
        height: 32px;
        width: 32px;
        cursor: pointer;
    }

    .title span{
        font-weight: 700;
        font-size: 12px;
    }

    .title h1{
        flex-grow: 1;
        font-size: 24px;
    }

    .item{
        padding: 16px 20px;
        color: white;
        height: 144px;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        position: relative;
    }

    .item .icon {
        padding: 0 8.3px;
        display: flex;
        justify-content: space-between;
        z-index: 3;
    }

    .item .icon svg{
        height: 24px;
        width: 24px;
        cursor: pointer;
    }

    svg:hover{
        color: rgb(242, 227, 227);
    }

    .item .image{
        position: absolute;
        bottom: -56px;
        height: 200px;
        left: 0;
        right: 0;
        display: flex;
        justify-content: center;
        z-index: 1;
    }

    .item .image img{
        margin-left: auto; 
        margin-right: auto; 
    }

    .pokeball{
        position: absolute;
        width: 208px;
        height: 208px;
        right: 8px;
        top: 8px;
        opacity: 0.1;
    }

    @media screen and (min-width: 768px) {

        .title h1{
            font-size: 35px;
        }
        .item .icon {
            padding: 0 25%;
        }

        .item .icon svg, .title svg{
            height: 55px;
            width: 55px;
        }
    }
</style>
