<template>

    <div class="seatCharts-row">

        <div class="seatCharts-space">
            {{index + 1}}
        </div>

        <div class="seatCharts-cell"
             v-bind:title="place.id"
             v-for="place in row.places">
            {{place.id}}
        </div>

        <button v-on:click="$emit('add-place', row.id)">+</button>
        <button v-on:click="$emit('remove-place', row.id)">-</button>

    </div>

</template>

<script>
  export default {
    name: "Rows",
    components:{},
    methods:{
    },
    props: {
      row:{},
      index:{
        Number
      }
    }
  }
</script>

<style scoped>

    .seatCharts-space{
        margin: 0px 10px 15px 0;
        width: 30px;
        padding-top: 5px;
    }
    .seatCharts-row{
        display: flex;
        justify-content: flex-start;
    }
    .seatCharts-cell{
        height: 30px;
        width: 30px;
        margin: 0 5px;
        background-color: #B9DEA0;
        border-radius: 5px;
        color: #fff;
        font-size: 14px;
        cursor: pointer;
    }
</style>