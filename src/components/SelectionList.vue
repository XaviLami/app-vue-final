<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0">
      <p>Aucun cours séléctionner</p>
    </div>
    <div v-else>
      <div
        v-for="classe in selection"
        :key="classe.name"
        class="border border-black my-4 p-2"
      >
        <h3>{{ classe.name }} ({{ classe.price }}€)</h3>
        <span>{{ classe.description }}</span>
        <img :src="require('../assets/img/' + classe.photo)" alt="">
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
}
</script>

<style>

</style>
