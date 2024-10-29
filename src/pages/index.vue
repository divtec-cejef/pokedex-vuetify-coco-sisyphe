<template>
  <v-container>
    <h1 class="mb-6 text-center">Pokédex : page d'accueil</h1>
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
      >{{ pokemon }}<pokemon-card :pokemon="pokemons" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  import { storeToRefs } from 'pinia'
  import { usePokemonStore } from '@/stores/pokemonStore'
  import PokemonCard from '@/components/PokemonCard.vue'

  // On récupère les données du store Pokemon
  const pokemonStore = usePokemonStore()
  // On transforme le store en refs (données réactives)
  const { pokemons } = storeToRefs(pokemonStore)
</script>
