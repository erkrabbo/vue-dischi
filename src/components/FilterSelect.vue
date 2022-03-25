<template>
  <select @change="$emit('filterList', getSel(), getType())" v-model="selected" class="ms-2 align-self-center" name="filter">
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
    dataFilterType: String,
    filteringBy: String
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

<style scoped>
  select{
    width: 200px;
  }

</style>
