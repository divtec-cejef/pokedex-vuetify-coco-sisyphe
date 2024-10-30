<template>
  <v-card
    height="445"
  >
    <v-img
      :alt="pokemon.name"
      :src="pokemonImage"
    />
    <v-card-title
      class="mt-6"
    >
      {{ pokemon.name }}
    </v-card-title>
    <v-card-subtitle>
      <v-chip
        v-for="type in pokemon.type.split(',')"
        :key="type"
        class="ml-2"
        :color="getTypeColor(type)"
      >
        {{ type }}
      </v-chip>
    </v-card-subtitle>
    <v-card-actions
      class="d-flex align-end justify-end"
    >
      <v-btn
        icon
        @click.prevent="toggleFavorite"
      >
        <v-icon :color="isFavorite ? 'grey' : ''">
          {{ isFavorite ? 'mdi-heart' : 'mdi-heart-outline' }}
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script setup>
  import { computed, defineProps } from 'vue'
  import { usePokemonStore } from '@/stores/pokemonStore'

  // Définit les props pour la constante pokemonImage
  const props = defineProps({
    pokemon: {
      type: Object,
      required: true,
    },
  })
  const pokemonImage = `/images/${removeAccents(props.pokemon.name.toLowerCase())}.png`
  const pokemonStore = usePokemonStore()
  const isFavorite = computed(() => pokemonStore.isFavorite(props.pokemon))

  // Fonction permettant de "d'enlever" les accents des noms
  // des Pokemons lors de la recherche de leur image correspondante
  function removeAccents (str) {
    return str
      .normalize('NFD') // Normalisation de la chaîne en décomposant les caractères (CGPT)
      .replace(/[\u0300-\u036f]/g, '') // Suppression des caractères d'accent (CGPT)
      .toLowerCase() // Conversion en minuscules (CGPT)
  }
  function toggleFavorite () {
    pokemonStore.toggleFavorite(props.pokemon)
  }
  function getTypeColor (type) {
    return pokemonStore.getTypeColor(type)
  }
</script>

<style scoped>

</style>
