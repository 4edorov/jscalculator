<template>
  <div id="app">
    <CalculatorTable/>
  </div>
</template>

<script>
import CalculatorTable from './components/CalculatorTable'

export default {
  name: 'app',
  components: {
    CalculatorTable
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
  display: flex;
  justify-content: center;
}
</style>
