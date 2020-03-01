<template>
    <div>
        <button v-on:click="$emit('add-row')">Добавить ряд</button>
        <button v-on:click="$emit('remove-row')">Удалить ряд</button>
<!--        <button v-on:click="$emit('add-row')">Добавить мест в ряде</button>-->
    </div>
</template>

<script>
  export default {
    name: "Settings",
    components: {},
    props:{
      rows:{}
    },
    methods: {
    }
  }
</script>

<style scoped>

</style>