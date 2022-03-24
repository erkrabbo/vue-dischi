<template>
  <div id="app">
    <header class="bg-secondary">
      <img src="https://png2png.com/wp-content/uploads/2021/07/spotify_logo_png1.png" alt="Spotify logo" width="80">
    </header>
    <main class="bg-dark">
      <div class="container">
        <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5 gy-2 gx-3">
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
$secondary: #2e3a46;
$dark: #1e2d3b;
@import "../node_modules/bootstrap/scss/bootstrap";
main{
  padding: auto{
    top: 5rem;
    bottom: 5rem;
  };
}

</style>
