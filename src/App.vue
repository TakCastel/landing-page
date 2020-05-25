<template>
  <div id="app">
    <h1>Brumes Roleplay</h1>
    <p>Bienvenue sur le site officiel de la Guilde Brumes.</p>
    <p>Avant de poursuivre, sélectionnez votre jeu.</p>
    <div class="banner">
      <img class="banner-item" src="../src/assets/JACKANNIVBAN_BORDER_LEFT_V1.png" alt="Bordure de bannière">
      <Card 
        v-for="(game, index) in games"
        :key="index"
        :redirectionLink="`https://${game.title}.brumes-rp.fr/`"
        :hoveredThumbnail="game.hoveredThumbnail"
        :backgroundImage="game.thumbnail"
        alternativeText="Jacket du jeu"
      />
      <img class="banner-item" src="../src/assets/JACKANNIVBAN_BORDER_RIGHT_V1.png" alt="Bordure de bannière">
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'

export default {
  name: 'app',
  components: {
    Card
  },

  data: () => ({
    games: [
      {
        title: 'wow',
        thumbnail: require('../src/assets/JACKANNIVBAN_BORDERWOW_V1.png'),
        hoveredThumbnail: require('../src/assets/JACKANNIVBAN_BORDERWOW_V2.png'),
      },
      {
        title: 'teso',
        thumbnail: require('../src/assets/JACKANNIVBAN_BORDERTESO_V1.png'),
        hoveredThumbnail: require('../src/assets/JACKANNIVBAN_BORDERTESO_V2.png'),
      },
      {
        title: 'swtor',
        thumbnail: require('../src/assets/JACKANNIVBAN_BORDERSW_V1.png'),
        hoveredThumbnail: require('../src/assets/JACKANNIVBAN_BORDERSW_V2.png'),
      },
      {
        title: 'ffxiv',
        thumbnail: require('../src/assets/JACKANNIVBAN_BORDERFF_V1.png'),
        hoveredThumbnail: require('../src/assets/JACKANNIVBAN_BORDERFF_V2.png'),
      }
    ]
  })
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Varela+Round');
@import url('https://fonts.googleapis.com/css?family=Varela+Round');

* {
  margin: 0;
}

body {
  min-height: 100vh;
  background: linear-gradient(-45deg, #212121, #252323);
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding-top: 56px;
  color: #ebe6e4;
}

.banner {
  display: flex;
  justify-content: center;
  margin-top: 28px;
}

.banner-item {
  width: 15vw /* Total must be < 100vw */
}
</style>
