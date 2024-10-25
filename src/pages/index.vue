<template>
  <v-container>
    <h1 class="mb-6 text-center">Pokédex</h1>
  </v-container>
  <v-container>
    <v-row>
      <v-col
        v-for="pokemon in pokemons"
        :key="pokemon.id"
        cols="5"
        lg="2"
      >
        <pokemon-card :pokemon="pokemon">{{pokemon}}</pokemon-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  import { storeToRefs } from 'pinia'
  import { usePokemonStore } from '@/stores/pokemonStore'
  // On récupère les données du store Pokemon
  const pokemonStore = usePokemonStore()
  // On transforme le store en refs (données réactives)
  const { pokemons } = storeToRefs(pokemonStore)
</script>
