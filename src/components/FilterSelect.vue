<template>
  <select @change="$emit('filterList', getSel(), getType())" v-model="selected" class="ms-auto me-3 align-self-center" name="filter">
    <option value="">All</option>
    <option v-for="(ele, index) in dataList" :value="ele" :key="index">{{ele}}</option>
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
    dataList: Array,
    dataFilterType: String
  },
  methods: {
    getSel () {
      return this.selected
    },
    getType () {
      return this.dataFilterType
    }
  }
}
</script>

<style>

</style>
