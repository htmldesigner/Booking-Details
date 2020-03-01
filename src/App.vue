<template>

<div id="app">
<div class="charts-settings">
  <Settings
    v-on:add-row="AddRow"
    v-on:remove-row="RemoveRow"
    v-bind:rows="rows"
  />
</div>
  <pre>
  </pre>
  <SeatCharts
     v-on:add-place="AddPlace"
     v-on:remove-place="RemovePlace"
     v-bind:rows="rows"
  />

</div>

</template>

<script>
  import Settings from "./components/Settings";
  import SeatCharts from './components/SeatCharts'
  export default {
    name: "App",
    components: {
      Settings, SeatCharts
    },
    data(){
      return {
        rows: [
          {id: 1, class: 'firstClass', price: '',
            places: [
              {id: 1, class: '',  state: 'available', price: ''},
              {id: 2, class: '',  state: 'available', price: ''},
              {id: 3, class: '',  state: 'available', price: ''},
              {id: 5, class: '',  state: 'available', price: ''},
              {id: 6, class: '',  state: 'available', price: ''},
              {id: 7, class: '',  state: 'available', price: ''},
              {id: 8, class: '',  state: 'available', price: ''},
              {id: 9, class: '',  state: 'available', price: ''},
              {id: 10, class: '',  state: 'available', price: ''},
            ]
          },
          {id: 2, class: 'firstClass', price: '',
            places: [
              {id: 1, class: '',  state: 'available', price: ''},
              {id: 2, class: '',  state: 'available', price: ''},
              {id: 3, class: '',  state: 'available', price: ''},
              {id: 5, class: '',  state: 'available', price: ''},
              {id: 6, class: '',  state: 'available', price: ''},
              {id: 7, class: '',  state: 'available', price: ''},
              {id: 8, class: '',  state: 'available', price: ''},
              {id: 9, class: '',  state: 'available', price: ''},
              {id: 10, class: '',  state: 'available', price: ''},
            ]
          },
          {id: 3, class: 'firstClass', price: '',
            places: [
              {id: 1, class: '',  state: 'available', price: ''},
              {id: 2, class: '',  state: 'available', price: ''},
              {id: 3, class: '',  state: 'available', price: ''},
              {id: 5, class: '',  state: 'available', price: ''},
              {id: 6, class: '',  state: 'available', price: ''},
              {id: 7, class: '',  state: 'available', price: ''},
              {id: 8, class: '',  state: 'available', price: ''},
              {id: 9, class: '',  state: 'available', price: ''},
              {id: 10, class: '',  state: 'available', price: ''},
            ]
          },
        ],
      }
    },
    computed:{
    },
    methods: {
      AddRow(){
        const newRow = {id: this.rows.length + 1, class: 'firstClass', price: '',
          places: [
            {id: 1, class: '',  state: 'available', price: ''},
          ]
        }
        this.rows.push(newRow)
        console.log(this.rows)
      },
      RemoveRow(){
        this.rows.pop()
      },
      // receive row id
      AddPlace(id){
        if(id){
          const addplace =  this.rows.filter(i => i.id == id)
          let currentId = addplace[0].places.length + 1
          addplace[0].places.push({id: currentId, class: '',  state: 'available', price: ''})
          console.log(addplace[0].places.length)
        }

      },
      // receive row id
      RemovePlace(id){
        const removeplace =  this.rows.filter(i => i.id == id)

        removeplace[0].places.pop()
        console.log(removeplace)
      },
    }
  }


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  justify-content: space-between;
  max-width: 1140px;
  margin: 0 auto;
}

.charts-settings{
  width: 300px;
  border: 1px solid #ccc;
  height: 300px;
  border-radius: 5px;
}

  .array{
    width: 300px;
  }

</style>
