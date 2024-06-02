<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="input-group">
      <label for="number1">Número 1:</label>
      <input type="number" v-model.number="number1" id="number1" />
    </div>
    <div class="input-group">
      <label for="operation">Operação:</label>
      <select v-model="operation" id="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <div class="input-group">
      <label for="number2">Número 2:</label>
      <input type="number" v-model.number="number2" id="number2" />
    </div>
    <div>
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      let result = 0;
      switch (this.operation) {
        case 'add':
          result = this.number1 + this.number2;
          break;
        case 'subtract':
          result = this.number1 - this.number2;
          break;
        case 'multiply':
          result = this.number1 * this.number2;
          break;
        case 'divide':
          result = this.number1 / this.number2;
          break;
      }
      return result;
    },
  },
};
</script>

<style scoped>
#app {
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  background: #f0f4f8;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  font-family: 'Arial', sans-serif;
}

h1 {
  color: #333;
  margin-bottom: 20px;
}

.input-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  color: #555;
}

input,
select {
  width: calc(100% - 20px);
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
}

input:focus,
select:focus {
  border-color: #007BFF;
  outline: none;
  box-shadow: 0 0 4px rgba(0, 123, 255, 0.25);
}

h2 {
  margin-top: 20px;
  padding: 10px;
  background: #e9ecef;
  border-radius: 4px;
  color: #333;
}
</style>
