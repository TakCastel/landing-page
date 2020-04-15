<template>
  <div id="app">
    <h1>Brumes Roleplay</h1>
    <p>Bienvenue sur le site officiel de la Guilde Brumes.</p>
    <p>Avant de poursuivre, sélectionnez votre jeu.</p>
    <div class="row">
      <Card 
        v-for="(game, index) in games"
        :key="index"
        :redirectionLink="`https://${game.title}.brumes-rp.fr/`"
        :backgroundImage="game.thumbnail ? game.thumbnail.url : undefined"
        alternativeText="Jacket du jeu"
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
  },

  data: () => ({
    games: [
      
    ]
  }),

  beforeMount() {
    const baseURI = 'https://brumes-api.herokuapp.com/'
      this.$http.get(`${baseURI}games`)
      .then((result) => {
        this.games = result.data
      })
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
