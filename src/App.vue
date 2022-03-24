<template>
  <div id="app">
    <header>
      <img src="https://cantabrialabsdifacooper.it/wp-content/uploads/2021/03/png-clipart-spotify-logo-spotify-computer-icons-podcast-music-apps-miscellaneous-angle.png" alt="Spotify logo" width="50">
    </header>
    <main>
      <div class="container">
        <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
          <spoty-card v-for="card in cards" :key="card.title" :card-data="card" />
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import axios from 'axios'
import SpotyCard from './components/SpotyCard.vue'

export default {
  name: 'App',
  data () {
    return {
      cards: null
    }
  },
  components: {
    SpotyCard
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then(result => {
        this.cards = result.data.response
        console.log(this.cards)
      })
  }
}
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
