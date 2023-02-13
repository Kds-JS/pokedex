<template>
  <div class="card">
    <div class="number">
        <div>
            <span>#044</span>
        </div>
    </div>

    <div class="image">
        <img src="../../assets/Silhouette.png" alt="image">
    </div>

    <div class="title">
        <span>Pokémon name</span>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
    .card{
        position: relative;
        height: 108px;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.2);
        border-radius: 8px;
    }
    .image{
        position: absolute;
        width: 72px;
        height: 72px;
        left: 0;
        right: 0;
        top: 16px;
        margin-left: auto; 
        margin-right: auto;
    }

    img{
        height: 100%;
        width: 100%;
    }

    .number{
        height: 64px;
    }

    .number div{
        display: flex;
        justify-content: flex-end;
        padding: 4px 8px;
        color: #666666;
        font-weight: 400;
        font-size: 8px;
    }

    .title{
        height: 44px;
        background: #EFEFEF;
        border-radius: 7px;
        display: flex;
        align-items: flex-end;
        justify-content: center;
        padding: 4px 4px;
    }

    .title span{
        font-weight: 400;
        font-size: 10px;
        color: #1D1D1D;
    }

    @media screen and (min-width: 1280px) {
        .title span{
            font-size: 14px;
        }

        .number div{
            font-size: 10px;
        }
    }
</style>
