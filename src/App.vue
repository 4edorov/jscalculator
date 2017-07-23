<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello></hello>
    <CalculatorTable></CalculatorTable>
  </div>
</template>

<script>
import Hello from './components/Hello'
import CalculatorTable from './components/CalculatorTable'

export default {
  name: 'app',
  components: {
    Hello,
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
}
</style>
