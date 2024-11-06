<template>
  <v-text-field
    v-model="search"
    class="px-4 mx-4"
    clearable
    label="Trouver un Pokémon"
    prepend-icon="mdi-magnify"
  />
</template>
<script setup>
  const search = defineModel()
</script>
