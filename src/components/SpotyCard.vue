<template>
  <div class="col">
    <div class="card">
      <img class="card-img-top" :src="cardData.poster" :alt="cardData.title">
      <h2 class="card-title">{{ cardData.title}}</h2>
      <div class="card-text">
        <p>{{ cardData.author}}</p>
        <p>{{ cardData.year }}</p>
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

</style>
