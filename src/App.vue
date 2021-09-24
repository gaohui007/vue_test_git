<template>
  <div id="app">
    <Search></Search>
    <List></List>
  </div>
</template>

<script>
import Test from './components/vuetest'
import Search from './components/Search'
import List from './components/List'

export default {
  name: 'App',
  components: {
    Test,
    Search,
    List
  }
}
</script>

<style>

</style>
