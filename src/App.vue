<template>
  <div id="app">
    <div class="calculator">
      <label for="num1">Número 1:</label>
      <input
        v-model="num1"
        type="number"
        id="num1"
        @input="calcularResultado"
      />

      <label for="operacao">Operação:</label>
      <select v-model="operacao" id="operacao" @change="calcularResultado">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <label for="num2">Número 2:</label>
      <input
        v-model="num2"
        type="number"
        id="num2"
        @input="calcularResultado"
      />

      <p>Resultado: {{ resultado }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: "+",
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case "+":
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case "-":
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case "*":
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case "/":
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>
* {
  font-family: Arial, Helvetica, sans-serif;
  margin: 0px;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #c0c0c0;
}

.calculator {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}

label {
  display: block;
  margin-bottom: 8px;
}

input,
select {
  font-size: 16px;
  width: 100%;
  padding: 8px;
  margin-bottom: 16px;
  box-sizing: border-box;
}

p {
  font-size: 18px;
  font-weight: bold;
  margin-top: 20px;
}
</style>
