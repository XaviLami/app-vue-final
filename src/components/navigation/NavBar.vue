<template>
  <div class="bg-blue-300 p-2">
    <a href="#" @click="changeComponent('player-view')">Tous les cours</a> |
    <a href="#" @click="changeComponent('selection-list')">Ma sélection</a>
  </div>
</template>

<script>
  export default {
    name: "nav-bar",
    methods: {
      changeComponent(value) {
        this.$emit('change-component', value)
      }
    }
  }
</script>

<style scoped>
.bg-blue-300{
  text-align: center;
}
  a{
    font-size: 20px;
  }
</style>
