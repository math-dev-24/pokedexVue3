<script setup lang="ts">

import type {Pokemon} from "@/interfaces/pokemon";

const props = defineProps<{
  pokemon: Pokemon
}>()

const emit = defineEmits<{
  (e: "detail", newName: String):void
}>()

</script>

<template>
  <div class="card">
    <div>{{pokemon.name}}</div>
    <template v-if="pokemon.type2">
      <div>{{pokemon.type1}} / {{pokemon.type2}}</div>
    </template>
    <template v-else>
      <div>{{pokemon.type1}}</div>
    </template>
    <button @click="emit('detail', pokemon.name)">Détail</button>
  </div>
</template>

<style scoped lang="sass">
.card
  width: 250px
  display: flex
  flex-direction: column
  justify-content: center
  align-content: center
  padding: 5px
  border: 1px solid cornflowerblue
  border-radius: 5px
  transition: all .4s ease

</style>
