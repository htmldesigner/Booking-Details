<template>
    <div>
        <div class="front-indicator">Front</div>

        <div class="seatCharts-container">

          <Rows
            v-on:add-place="AddPlace"
            v-on:remove-place="RemovePlace"
            v-for="(row, index) of rows"
            v-bind:index="index"
            v-bind:row="row"
          />

        </div>

    </div>
</template>

<script>
  import Rows from "./Rows";

  export default {
    name: "SeatCharts",
    components: {
      Rows
    },
    methods:{
      AddPlace(id){
        this.$emit('add-place', id)
      },
      RemovePlace(id){
        this.$emit('remove-place', id)
      }
    },
    props: {
      rows: {}
    }
  }
</script>

<style scoped>

    .seatCharts-container {
        min-width: 500px;
        /*margin: 0 auto;*/
        display: flex;
        flex-direction: column;
        /*justify-content: space-between;*/
        border: 1px solid #ccc;
        padding: 20px;
        height: autopx;
    }

    .front-indicator {
        width: 160px;
        margin: 10px auto 20px auto;
        background-color: #f6f6f6;
        color: #adadad;
        text-align: center;
        padding: 3px;
        border-radius: 5px;
    }

</style>