<template>
  <div class="calculator-container">
    <div class="calculator-title">Simple Calculator</div>
    <div class="calculator">
      <input type="text" v-model="input" readonly class="calculator-screen" />
      <div class="function-buttons">
        <button @click="clear" class="button button-clear">C</button>
        <button @click="calculate" class="button button-equal">=</button>
      </div>
      <div class="buttons">
        <button @click="append('7')" class="button">7</button>
        <button @click="append('8')" class="button">8</button>
        <button @click="append('9')" class="button">9</button>
        <button @click="append('/')" class="button button-operator">/</button>
        <button @click="append('4')" class="button">4</button>
        <button @click="append('5')" class="button">5</button>
        <button @click="append('6')" class="button">6</button>
        <button @click="append('*')" class="button button-operator">*</button>
        <button @click="append('1')" class="button">1</button>
        <button @click="append('2')" class="button">2</button>
        <button @click="append('3')" class="button">3</button>
        <button @click="append('-')" class="button button-operator">-</button>
        <button @click="append('0')" class="button button-zero">0</button>
        <button @click="append('+')" class="button button-operator">+</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: ''
    };
  },
  methods: {
    append(value) {
      this.input += value; // Append the clicked button value to the input
    },
    clear() {
      this.input = ''; // Clear the input
    },
    calculate() {
      try {
        this.input = eval(this.input).toString(); // Evaluate the input expression
      } catch (error) {
        this.input = 'Error'; // Handle any evaluation errors
        setTimeout(() => this.clear(), 1500); // Clear input after showing Error
      }
    }
  }
};
</script>

<style scoped>
.calculator-container {
  width: 400px;
  margin: 100px auto;
  background: linear-gradient(135deg, #e0e0e0, #ffffff);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
  padding: 20px;
}

.calculator-title {
  text-align: center;
  font-size: 28px;
  font-weight: bold;
  color: #4285f4;
  margin-bottom: 20px;
  padding: 10px;
  border-radius: 8px;
  background-color: #f1f3f4;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
  transition: background-color 0.3s;
}

.calculator-title:hover {
  background-color: #e0e0e0; 
}

.calculator {
  background: #fff;
  border-radius: 12px;
  padding: 15px;
}

.calculator-screen {
  width: 100%;
  height: 60px;
  text-align: right;
  font-size: 34px;
  border: none;
  border-radius: 8px;
  margin-bottom: 15px;
  padding: 10px;
  background-color: #f5f5f5;
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
}

.function-buttons {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
  margin-bottom: 15px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.button {
  padding: 20px;
  font-size: 28px;
  border: none;
  border-radius: 8px;
  background-color: #e0e0e0;
  color: #333;
  transition: background-color 0.2s ease, transform 0.1s;
}

.button:hover {
  background-color: #d5d5d5;
}

.button-operator {
  background-color: #f9a825;
  color: white;
}

.button-operator:hover {
  background-color: #f57f17;
}

.button-equal {
  background-color: #4caf50;
  color: white;
}

.button-equal:hover {
  background-color: #388e3c;
}

.button-clear {
  background-color: #f44336;
}

.button-clear:hover {
  background-color: #d32f2f;
}

.button-zero {
  grid-column: span 2; 
}
</style>