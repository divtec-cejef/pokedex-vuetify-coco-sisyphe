<template>
  <v-app-bar flat>
    <v-container class="d-flex align-start align-center">
      <v-avatar
        class="mr-4 pa-0 cursor-pointer"
        image="@/assets/pokeball.svg"
        size="64"
        @click="$router.push('/')"
      />
      <v-toolbar-title>Pokédex</v-toolbar-title>
      <v-btn
        v-for="link in menuItems"
        :key="link.title"
        :icon="link.icon"
        :to="link.path"
      />
    </v-container>
  </v-app-bar>
</template>

<script setup>
  import { reactive } from 'vue'
  import { createRouter as $router } from 'vue-router'

  const menuItems = reactive([
    { title: 'Accueil', path: '/', icon: 'mdi-pokeball' },
    { title: 'Favori', path: '/Favoris', icon: 'mdi-heart-multiple-outline' },
    { title: 'FAQ', path: '/FAQ', icon: 'mdi-forum-outline' },
    { title: 'KantoMap', path: '/KantoMap', icon: 'mdi-map-outline' },
  ])
</script>
