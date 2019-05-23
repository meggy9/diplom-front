<template>
  <div id="app">
    <h1>Реестр поставщиков соц. услуг</h1>
    <FilterForm />
  </div>
</template>

<script>
import FilterForm from './components/FilterForm.vue'

export default {
  name: 'app',
  components: { FilterForm },
  data() {
    return {
      objectsList: []
    }
  },
  methods: {
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
