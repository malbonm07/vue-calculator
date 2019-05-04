<template>
  <div class="hello">
    <div class="container">
      <div class="calculator-screen">
        <div class="calculator-result">
          <h2 class="calculator-result__numbers" :class="{'longResult' : value.length > 16}">{{value || "0"}}</h2>
        </div>
      </div>
      <div class="body-calculator">
        <div class="button clear" @click="clearScreen('0')">C</div>
        <div class="button symbol">+/-</div>
        <div class="button symbol" @click="percent()">%</div>
        <div class="button math" @click="operationDivide()">/</div>
        <div class="button" @click="mathNumber('7')">7</div>
        <div class="button" @click="mathNumber('8')">8</div>
        <div class="button" @click="mathNumber('9')">9</div>
        <div class="button math" @click="operationMulti()">*</div>
        <div class="button" @click="mathNumber('4')">4</div>
        <div class="button" @click="mathNumber('5')">5</div>
        <div class="button" @click="mathNumber('6')">6</div>
        <div class="button math" @click="operationRes()">-</div>
        <div class="button" @click="mathNumber('1')">1</div>
        <div class="button" @click="mathNumber('2')">2</div>
        <div class="button" @click="mathNumber('3')">3</div>
        <div class="button math" @click="operationAdd()">+</div>
        <div class="button span2" @click="mathNumber('0')">0</div>
        <div class="button">.</div>
        <div class="button result" @click="operationResult()">=</div>
      </div>
    </div>
    <div class="app-logo">
      <img alt="Vue logo" src="../assets/logo.png" width="100%">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      operation: null,
      previous: null,
      value: "",
      readyToSwitch: false,
      readyToOperate: false,
    }
  },
  methods: {
    mathNumber(number) {
      if(this.readyToOperate) {
        this.value = number;
        this.readyToOperate = false;
      }else if (this.value === "0"){
        this.value = number;
      }else if(this.value != "0") {
        this.value += number;
      }
    },
    clearScreen() {
      this.value = "";
      this.previous = "";
      this.readyToOperate = false;
      this.readyToSwitch = false;
    },
    percent() {
      if(!this.value) {
        return
      }
      this.value = `${parseFloat(this.value)/ 100}`
    },
    operationAdd() {
      if(!this.readyToOperate) {
        this.readyToSwitch = false;
      }
      if(this.readyToOperate) {
        this.operation = (a,b) => a + b;
      }
      if(this.value && !this.readyToSwitch) {
        this.previous = this.value;
        this.readyToSwitch = true;
        this.operation = (a,b) => a + b;
        this.value = "0";
      }
    },
    operationRes() {
      if(!this.readyToOperate) {
        this.readyToSwitch = false;
      }
      if(this.readyToOperate) {
        this.operation = (a,b) => b - a;
      }
      if(this.value && !this.readyToSwitch) {
        this.previous = this.value;
        this.readyToSwitch = true;
        this.operation = (a,b) => b - a;
        this.value = "0";
      }
    },
    operationMulti() {
      if(!this.readyToOperate) {
        this.readyToSwitch = false;
      }
      if(this.readyToOperate) {
        this.operation = (a,b) => a * b;
      }
      if(this.value && !this.readyToSwitch) {
        this.previous = this.value;
        this.readyToSwitch = true;
        this.operation = (a,b) => a * b;
        this.value = "0";
      }
    },
    operationDivide() {
      if(!this.readyToOperate) {
        this.readyToSwitch = false;
      }
      if(this.readyToOperate) {
        this.operation = (a,b) => b / a;
      }
      if(this.value && !this.readyToSwitch) {
        this.previous = this.value;
        this.readyToSwitch = true;
        this.operation = (a,b) => b / a;
        this.value = "0";
      }
    },
    operationResult() {
      if(this.value != "0" && this.previous) {
        this.value = `${this.operation(parseFloat(this.value), parseFloat(this.previous))}`;
        this.previous = this.value
        this.readyToOperate = true;
      }else if(!this.value) {
        this.value = this.previous;
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../scss/styles";
</style>
