<template>
  <select class="ms-auto me-3 align-self-center" name="filter">
    <option v-for="(ele, index) in dataGenresList" value="1" :key="index">{{ele}}</option>
  </select>
</template>

<script>
export default {
  name: 'FilterSelect',
  props: {
    dataGenresList: Array
  }
}
</script>

<style>

</style>
