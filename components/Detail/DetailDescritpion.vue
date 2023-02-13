<template>
  <section>
    <div class="type">
        <span>Grass</span>
        <span>Type</span>
    </div>
    <h2>About</h2>
    
    <div class="attribute">
        <div>
            <span>
                <Icon icon="akar-icons:shopping-bag"/>
                9,9 kg
            </span>
            <p>Weight</p>
        </div>

        <div>
            <span class="straighten">
                <Icon icon="material-symbols:straighten-outline"/>
                9,9 m
            </span>
            <p>Height</p>
        </div>

        <div>
            <span>
                Abillity 1
            </span>
            <span>
                Abillity 2
            </span>
            <p>Moves</p>
        </div>

    </div>

    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nesciunt distinctio accusamus fuga.</p>

    <h2>Base Stats</h2>

    <Stats/>

  </section>
</template>

<script setup>
    import { Icon } from '@iconify/vue';
    import Stats from './Stats.vue';
</script>

<style scoped>
    section{
        background-color: white;
        box-shadow: inset 0px 1px 3px 1px rgba(0, 0, 0, 0.25);
        border-radius: 8px;
        padding: 56px 20px 20px 20px;
        font-size: 10px;
    }

    p{
        font-weight: 400;
        text-align: justify;
    }
    .type{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 16px;
    }

    .type span {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2px 8px;
        height: 20px;
        background: #666666;
        color: white;
        font-size: 12px;
        border-radius: 10px;
    }

    h2{
        font-weight: 700;
        font-size: 14px;
        color: #B8B8B8;
        text-align: center;
        margin: 16px 0;
    }

    .attribute{
        margin: 16px 0;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }

    .attribute svg{
        height: 16px;
        width: 16px;
    }

    .attribute div{
        border-right: 2px solid silver;
        height: 48px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 8px;
    }
    .attribute div:last-child{
        border: none;
        gap: 4px;
    }

    .attribute div p{
        font-size: 8px;
    }

    .attribute div span{
        display: flex;
        align-items: center;
        gap: 8px;
    }

    .straighten svg{
        transform : rotate(90deg);
    }

    @media screen and (min-width: 768px) {
        section, .attribute div p, .type span {
            font-size: 16px;
        }

        p{
            text-align: center;
        }

        .type span {
            padding: 12px 20px;
        }

        h2{
            font-size: 18px;
        }
    }
</style>
