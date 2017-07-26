<template>
  <b-form-input class="display" v-model="input" type="text">
  </b-form-input>
</template>

<script>
export default {
  name: 'DisplayTable',
  props: ['input']
}
</script>

<style scoped>
.display {
  height: 100%;
  width: 95%;
  margin-top: 10px;
  margin-left: auto;
  margin-right: auto;
  border: solid;
  border-color: black;
  border-radius: 10px;
  background-color: #e0ebeb;
  text-align: right;
  font-size: 300%;
  font-family: Ubuntu, sans-serif;
}
</style>
