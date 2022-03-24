<template>
  <div class="col d-flex">
    <div class="card text-center border-0 bg-secondary">
      <div class="card-body">
        <img class="card-img-top" :src="cardData.poster" :alt="cardData.title">
        <h2 class="card-title text-white mt-2">{{ cardData.title}}</h2>
        <div class="card-text">
          <span>{{ cardData.author}}</span>
          <p>{{ cardData.year }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SpotyCard',
  props: {
    cardData: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .card-text{
    color: grey;
  }
</style>
