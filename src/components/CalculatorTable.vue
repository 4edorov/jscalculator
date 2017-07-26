<template>
  <div class="main">
    <div class="display-part">
      <DisplayTable :input="input">
      </DisplayTable>
    </div>
    <div class="buttons-part">
      <div v-for="row in buttonsRows" class="button-rows">
        <div v-for="button in row">
          <b-button size="sm" variant="primary" class="button" v-on:click="pressOnButton(button)">
            {{button}}
          </b-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import DisplayTable from './DisplayTable'

export default {
  name: 'CalculatorTable',
  data () {
    return {
      buttonsRows: [
        ['7', '8', '9', '/', 'AC'],
        ['4', '5', '6', '*', 'CE'],
        ['1', '2', '3', '-', '='],
        ['0', '.', '+', '+', '=']
      ],
      input: ''
    }
  },
  components: {
    DisplayTable
  },
  methods: {
    pressOnButton (value) {
      if (value !== '=') {
        this.input += value
      } // else {
      //   this.input = eval(this.input)
      // }
    }
  }
}
</script>

<style scoped>
.main {
  width: 350px;
  height: 370px;
  background-color: #85adad;
  border: solid;
  border-color: black;
  border-radius: 10px;
}

.display-part {
  height: 35%;
}

.buttons-part {
  height: 65%;
}

.button-rows {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  margin-top: 10px;
}

.button {
  min-width: 60px;
  min-height: 40px;
}
</style>
