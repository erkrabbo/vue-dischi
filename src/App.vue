<template>
  <div id="app">
    <header class="bg-secondary">
      <img src="https://png2png.com/wp-content/uploads/2021/07/spotify_logo_png1.png" alt="Spotify logo" width="80">
    </header>
    <main class="bg-dark">
      <div class="container">
        <div v-if="cards != null" class="row row-cols-2 row-cols-md-4 row-cols-lg-5 gy-3 gx-2 gx-xl-3 gx-xxl-5">
          <spoty-card v-for="card in cards" :key="card.title" :card-data="card" />
        </div>
        <div v-else class="splash d-flex text-align-center">
          <div class="circle">
            <div class="bar"></div>
          </div>
          <span class="m-auto">Loading songs..</span>
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
    setTimeout(() => axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then(result => {
        this.cards = result.data.response
        console.log(this.cards)
      }), 3000)
  }
}
</script>

<style lang="scss">
$secondary: #2e3a46;
$dark: #1e2d3b;
@import "../node_modules/bootstrap/scss/bootstrap";
#app{
  height: 100vh;
  overflow: hidden;
}
main{
  height: calc(100% - 50px);
  overflow: auto;
  padding: auto{
    top: 5rem;
    bottom: 5rem;
  };
}
.splash{
  position: fixed;
  top: 50%;
  left: 50%;

  transform: translate(-50%, -50%);

  color: white;

  .circle{
    border: 3px solid white;
    border-radius: 50%;

    position: relative;
    width: 50px;
    height: 50px;

    margin-right: 1em;
      .bar{
        position: absolute;
        top: calc(50% - 4px);
        left: -3px;

        width: 56px;
        height: 8px;

        background: $dark;
        z-index: 50;

        animation: rotate 1.5s linear infinite;
      }
      @keyframes rotate {
        from {transform: rotate(0deg);}
        to {transform: rotate(360deg);}
      }
    }
}

</style>
