<template>
  <div class="calculator">
    <input type="number" v-model="number1" @input="calculate" />
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="number2" @input="calculate" />
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operator: "+",
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case "+":
          this.result = this.number1 + this.number2;
          break;
        case "-":
          this.result = this.number1 - this.number2;
          break;
        case "*":
          this.result = this.number1 * this.number2;
          break;
        case "/":
          this.result = this.number1 / this.number2;
          break;
        default:
          this.result = 0;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

input[type="number"],
select {
  margin-bottom: 10px;
}
</style>
