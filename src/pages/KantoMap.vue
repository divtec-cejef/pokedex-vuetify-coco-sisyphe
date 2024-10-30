<script setup>
</script>

<template>
  <v-container>
    <h1 class="mb-6 text-center">Monde Pokemon</h1>
  </v-container>
  <v-container>
    <div class="text-center py-2">
      <v-btn @click="dialog = true">
        Carte du Monde Pokemon
      </v-btn>

      <v-dialog
        v-model="dialog"
        max-width="1200"
      >
        <v-card
          prepend-icon="mdi-map"
          title="Carte du monde de Pokemon"
        >
          <v-img
            src="/images/pokemon-map.png"
          />
          <template #actions>
            <v-btn
              class="ms-auto"
              text="Ok"
              @click="dialog = false"
            />
          </template>
        </v-card>
      </v-dialog>
    </div>
  </v-container>
  <v-card>
    <div class="text-left pa-8 d-flex flex-wrap gr-4">
      <div>
        <h2>Un univers fascinant à découvrir</h2>
        <p class="v-card-text">Le monde Pokémon est un vaste et merveilleux univers peuplé de créatures extraordinaires
          appelées Pokémon.
          Cette carte représente les différentes régions que les dresseurs peuvent explorer, chacune offrant ses propres
          défis, Pokémon uniques et aventures palpitantes.</p>
      </div>
      <div>
        <h2>Des régions diversifiées</h2>
        <p class="v-card-text">De Kanto à Galar, en passant par Johto, Hoenn, Sinnoh, Unova, Kalos et Alola, chaque
          région du monde Pokémon
          possède sa propre identité, sa culture et son écosystème unique. Les paysages varient des montagnes enneigées
          aux îles tropicales, offrant une diversité incroyable d'habitats pour les différentes espèces de Pokémon.</p>
      </div>
      <div>
        <h2>Un monde en constante évolution</h2>
        <p class="v-card-text">Le monde Pokémon est en perpétuelle expansion, avec de nouvelles régions, de nouvelles
          espèces de Pokémon et de
          nouvelles aventures qui sont régulièrement découvertes. Cette carte n'est qu'un aperçu d'un univers riche et
          en
          constante évolution, prêt à être exploré par les dresseurs audacieux.</p>
      </div>
      <div>
        <h2>Un appel à l'aventure</h2>
        <p class="v-card-text">Que vous soyez un dresseur débutant ou expérimenté, le monde Pokémon vous invite à partir
          à l'aventure.
          Capturez de nouveaux Pokémon, affrontez des champions d'arènes, déjouez les plans des équipes malveillantes et
          devenez peut-être le prochain Maître Pokémon. L'aventure commence ici, sur cette carte, mais où vous
          mènera-t-elle ?</p>
      </div>
    </div>
  </v-card>
</template>
<script>
  export default {
    data () {
      return {
        dialog: false,
      }
    },
  }
</script>
<style scoped>

</style>
