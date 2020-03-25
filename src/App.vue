<template>
  <div id="app">
    <h1>Brumes Roleplay</h1>
    <p>Bienvenue sur le site officiel de la Guilde Brumes.</p>
    <p>Avant de porusuivre, sélectionnez votre jeu.</p>
    <div class="row">
      <Card 
        isDisabled
        redirectionLink=""
        :backgroundImage="require('./assets/bg-ffxiv.jpg')"
        alternativeText="Fond d'écran de Final Fantasy XIV"
      />
      <Card
        redirectionLink="https://teso.brumes-rp.fr/"
        :backgroundImage="require('./assets/bg-teso.jpg')"
        alternativeText="Fond d'écran de The Elder Scrolls Online"
      />
      <Card
        isDisabled
        redirectionLink=""
        :backgroundImage="require('./assets/bg-wow.jpg')"
        alternativeText="Fond d'écran de World of Warcraft"
      />
      <Card 
        isDisabled
        redirectionLink=""
        :backgroundImage="require('./assets/bg-swtor.jpg')"
        alternativeText="Fond d'écran de Star Wars The Old Republic"
      />
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'

export default {
  name: 'app',
  components: {
    Card
  }
}
</script>

<style>
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

.row {
  display: flex;
  justify-content: space-evenly;
  margin-top: 28px;
}
</style>
