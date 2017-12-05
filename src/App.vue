<template>
  <div id="app">
    <FullCalendar/>
  </div>
</template>


<script>
import FullCalendar from './components/FullCalendar'

export default {
  name: 'app',
  components: {
    FullCalendar
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
