<template>
  <div class="stats">
    <div class="labels">
        <span>HP</span>
        <span>HP</span>
        <span>DOP</span>
        <span>SHP</span>
        <span>HP</span>
        <span>HPUI</span>
    </div>

    <div class="charts">
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
        <div>
            <span>999</span>
            <div>
                <div id="chart">

                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script setup>

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
        color: #B8B8B8;
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

    #chart{
        width: 45%;
        background: #B8B8B8;
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
