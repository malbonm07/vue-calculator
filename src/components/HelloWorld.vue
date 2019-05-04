<template>
  <div class="hello">
    <div class="container">
      <div class="calculator-screen">
        <div class="calculator-result">
          <h2 class="calculator-result__numbers">1234567890</h2>
        </div>
      </div>
      <div class="body-calculator">
        <div class="button">C</div>
        <div class="button">+/-</div>
        <div class="button">%</div>
        <div class="button">/</div>
        <div class="button">7</div>
        <div class="button">8</div>
        <div class="button">9</div>
        <div class="button">*</div>
        <div class="button">4</div>
        <div class="button">5</div>
        <div class="button">6</div>
        <div class="button">-</div>
        <div class="button">1</div>
        <div class="button">2</div>
        <div class="button">3</div>
        <div class="button">+</div>
        <div class="button span2">0</div>
        <div class="button">.</div>
        <div class="button">=</div>
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
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../scss/styles";
</style>
