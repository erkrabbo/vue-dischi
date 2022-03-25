<template>
  <select @change="$emit('filterList', sel())" v-model="selected" class="ms-auto me-3 align-self-center" name="filter">
    <option value="">All</option>
    <option v-for="(ele, index) in dataGenresList" :value="ele" :key="index">{{ele}}</option>
  </select>
</template>

<script>
export default {
  name: 'FilterSelect',
  data () {
    return {
      selected: ''
    }
  },
  props: {
    dataGenresList: Array
  },
  methods: {
    sel () {
      return this.selected
    }
  }
}
</script>

<style>

</style>
