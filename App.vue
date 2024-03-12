<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'addition'
    };
  },
  methods: {
    calculateResult() {
      switch (this.operation) {
        case 'addition':
          return parseFloat(this.num1) + parseFloat(this.num2);
        case 'subtraction':
          return parseFloat(this.num1) - parseFloat(this.num2);
        case 'multiplication':
          return parseFloat(this.num1) * parseFloat(this.num2);
        case 'division':
          return parseFloat(this.num1) / parseFloat(this.num2);
        default:
          return 0;
      }
    }
  }
};
</script>

<template>
  <div class="container mt-5">
    <div class="form-group">
      <label for="number1">Número 1:</label>
      <input type="number" class="form-control" id="number1" v-model="num1">
    </div>
    <div class="form-group">
      <label for="number2">Número 2:</label>
      <input type="number" class="form-control" id="number2" v-model="num2">
    </div>
    <div class="form-group">
      <label for="operation">Operação:</label>
      <select class="form-control" id="operation" v-model="operation">
        <option value="addition">Adição (+)</option>
        <option value="subtraction">Subtração (-)</option>
        <option value="multiplication">Multiplicação (*)</option>
        <option value="division">Divisão (/)</option>
      </select>
    </div>
    <div class="form-group">
      <label for="result">Resultado:</label>
      <input type="text" class="form-control" id="result" :value="calculateResult()" readonly>
    </div>
  </div>
</template>


