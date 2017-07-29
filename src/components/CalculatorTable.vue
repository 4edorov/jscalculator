<template>
  <div class="main">
    <div class="display-part">
      <DisplayTable :input="input"/>
    </div>
    <div class="buttons-part">
      <div v-for="row in buttonsRows" class="button-rows">
        <div v-for="button in row">
          <b-button size="sm" :variant="styleButton(button)" class="button" v-on:click="pressOnButton(button)">
            {{button}}
          </b-button>
        </div>
      </div>
    </div>
    <b-badge pill variant="warning">4edorator</b-badge>
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
        ['0', '.', '(', '+', ')']
      ],
      input: '0',
      pressCount: 0
    }
  },
  components: {
    DisplayTable
  },
  methods: {
    pressOnButton (value) {
      if (this.pressCount === 0) {
        this.input = ''
      }

      if (this.pressCount === 0 && (value === '/' || value === '*' || value === 'AC' || value === 'CE' || value === ')')) {
        this.input = '0'
        return
      }

      if (value === 'AC') {
        this.input = '0'
        this.pressCount = 0
        return
      }

      if (value === '=') {
        if (this.input.substr(-1).search(/[)\d]/) === 0) {
          try {
            this.input = eval(this.input.replace(/[^-()\d/*+.]/, '') || 0).toString()
          } catch (e) {
            this.input = e.message
            setTimeout(() => {
              this.input = '0'
              this.pressCount = 0
            }, 1500)
          }
          this.pressCount = 0
        } else {
          this.input = '0'
          this.pressCount = 0
        }
        return
      }

      this.pressCount++

      this.input += value
    },
    styleButton (value) {
      if (value === 'AC' || value === 'CE') {
        return 'danger'
      }
      if (value === '=') {
        return 'success'
      }
      return 'primary'
    }
  }
}
</script>

<style scoped>
.main {
  width: 350px;
  height: 400px;
  background-color: #85adad;
  border: solid;
  border-color: black;
  border-radius: 10px;
}

.display-part {
  height: 35%;
}

.buttons-part {
  height: 52%;
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
