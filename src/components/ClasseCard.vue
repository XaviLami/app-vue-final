<template>
  <div 
    class="border m-2 p-2 flex justify-between"
    :class="healthStyle"
  >
    <div>
      <h1 class="text-lg font-bold">{{ playerName }}</h1>
      <p> {{ playerProfUp }} </p>
    </div>
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "player-card",
  props: ['player'],
  computed: {
    playerName(){
      if(this.player.name.split('.').length > 1){
        return this.player.name.split('.')[1]
      }
      return this.player.name;
    },
    playerProfUp(){
      return this.player.prof.toUpperCase()
    },
    isInjured() {
      if(this.player.health == "out"){
        return true
      }
      return false
    },
    healthStyle() {
      return { 
        'bg-gray-600': this.isInjured, 
        'border-white': this.isInjured, 
        'border-black': !this.isInjured 
      }
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-player', this.player)
    }
  }
}
</script>

<style scoped>

</style>
