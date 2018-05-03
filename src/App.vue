<template>
  <div id="app">
    <Header/>
    <SongList/>
  </div>
</template>

<script>
import SongList from './components/SongList.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  components: {
    SongList,
    Header
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: left;
}
</style>
