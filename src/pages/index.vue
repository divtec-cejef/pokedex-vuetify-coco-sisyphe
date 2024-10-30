<template>
  <v-container>
    <h1 class="mb-6 text-center">Pokédex</h1>
  </v-container>
  <v-container>
    <v-row>
      <v-col
        v-for="pokemon in pokemons"
        :key="pokemon.id"
        cols="6"
        lg="3"
        md="4"
        sm="6"
      >
        <pokemon-card :pokemon="pokemon" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  import { usePokemonStore } from '@/stores/pokemonStore'
  import { storeToRefs } from 'pinia'

  // Récupère le magasin des Pokémons
  const pokemonStore = usePokemonStore()

  /* Récupère les données pokemons, selectedPokemon, favorites
  * et les transforme directement en refs (données réactives) dans le composant
  * Elles sont donc directement accessibles dans le template HTML
  *
  * Attention à ne pas oublier le .value dans le <script> pour accéder à la valeur
  * comme pour les autre refs.
  */
  const { pokemons } = storeToRefs(pokemonStore)
</script>
