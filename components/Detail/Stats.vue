<template>
  <div class="stats">
    <div class="labels">
        <span v-for="element in pokemon.stats" :key="element.stat.name" :style="{color:  color[pokemon.types[0].type.name]}">
            {{ element.stat.name }}
        </span>
        
    </div>

    <div class="charts">
        <div v-for="element in pokemon.stats" :key="element.stat.name">
            <span>{{ element.base_stat }}</span>
            <div>
                <div :style="{ width: element.base_stat + '%', backgroundColor:  color[pokemon.types[0].type.name]}">

                </div>
            </div>
        </div>
        
    </div>
  </div>
</template>

<script setup>
    import {color} from '../../utils/color';
    const { pokemon} = defineProps(['pokemon'])
    // console.log(color);
</script>

<style scoped>

.stats{
    display: flex;
    align-items: center;
    font-size: 10px;
}
    .labels{
        display: flex;
        flex-direction: column;
        gap: 4px;
    }

    .labels span{
        font-weight: 700;
    }

    .charts{
        flex-grow: 1;
        border-left: 2px solid silver;
        padding: 0 8px;
        margin-left: 12px;
        display: flex;
        flex-direction: column;
        gap: 4px;
    }

    .charts div{
        display: flex;
        align-items: center;
        gap: 8px;
    }

    .charts div span{
        color: #1D1D1D;
    }
    .charts div div{
        height: 4px;
        border-radius: 4px;
        background-color: #F1F1F1;
        width: 100%;
    }


    

    @media screen and (min-width: 768px) {
        .stats{
            font-size: 14px;
        }

        .charts div div{
            height: 6px;
        }
    }
</style>
