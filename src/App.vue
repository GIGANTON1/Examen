<template>
  <div id="app">

    <ConversionMoneda/>
  </div>
</template>

<script>
import ConversionMoneda from './components/ConversionMoneda'

export default {
  name: 'app',
  components: {
      ConversionMoneda,
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
