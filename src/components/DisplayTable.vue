<template>
  <b-form-input class="display" v-model="input" type="text" disabled v-bind:style="fontSize">
  </b-form-input>
</template>

<script>
export default {
  name: 'DisplayTable',
  props: ['input'],
  computed: {
    fontSize () {
      if (this.input.length > 11) {
        return {
          'font-size': '150%'
        }
      }
      return {
        'font-size': '300%'
      }
    }
  }
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
  font-family: Ubuntu, sans-serif;
}
</style>
