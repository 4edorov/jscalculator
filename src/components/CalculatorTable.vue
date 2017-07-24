<template>
  <div>
    <div v-for="row in buttonsRows">
      <div v-for="button in row">
        <b-button size="sm" variant="primary">
          {{button}}
        </b-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalculatorTable',
  data () {
    return {
      buttonsRows: [
        ['7', '8', '9', '/', 'AC'],
        ['4', '5', '6', '*', 'CE'],
        ['1', '2', '3', '-', '='],
        ['0', '.', '+', '+', '=']
      ]
    }
  }
}
</script>

<style scoped>
</style>
