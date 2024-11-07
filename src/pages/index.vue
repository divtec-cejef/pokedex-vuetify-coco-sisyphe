<template>
  <v-container>
    <h1 class="mb-6 text-center">Pokédex</h1>
  </v-container>
  <search-bar v-model="search" />
  <v-container>
    <v-row>
      <v-col
        v-for="pokemon in filteredPokemons"
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
  import { computed, ref } from 'vue'
  import { storeToRefs } from 'pinia'
  import { usePokemonStore } from '@/stores/pokemonStore'
  import PokemonCard from '@/components/PokemonCard.vue'
  import SearchBar from '@/components/SearchBar.vue'

  // Récupère le magasin des Pokémons
  const pokemonStore = usePokemonStore()

  /* Récupère les données pokemons, selectedPokemon, favorites
  * et les transforme directement en refs (données réactives) dans le composant
  * Elles sont donc directement accessibles dans le template HTML
  *
  * Attention à ne pas oublier le .value dans le <script> pour accéder à la valeur
  * comme pour les autre refs.
  */
  const { pokemons } = storeToRefs(pokemonStore) // Utilise le getter filteredPokemons
  const search = ref('')
  const filteredPokemons = computed(() => {
    if (!search.value) return pokemons.value
    return pokemons.value.filter(pokemon =>
      pokemon.name.toLowerCase().includes(search.value.toLowerCase())
    )
  })

</script>
