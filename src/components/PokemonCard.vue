<template>
  <v-card :to="`/pokemon/${pokemon.id}`">
    <v-img :src="`images`" />
    <v-card-title>{{ pokemon.name }}</v-card-title>
    <v-card-subtitle />
    <v-card-text>Niveau: </v-card-text>
  </v-card>
</template>

<script setup>
  import { usePokemonStore } from '@/stores/pokemonStore'
</script>

<style scoped>

</style>
