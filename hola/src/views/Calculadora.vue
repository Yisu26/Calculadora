<template>
  <div id="app">
    <div class="calculator">
      <input type="text" v-model="current" disabled />
      <div class="buttons">
        <button @click="clear">C</button>
        <button @click="append('1')">1</button>
        <button @click="append('2')">2</button>
        <button @click="append('3')">3</button>
        <button @click="append('+')">+</button>
        <button @click="append('4')">4</button>
        <button @click="append('5')">5</button>
        <button @click="append('6')">6</button>
        <button @click="append('-')">-</button>
        <button @click="append('7')">7</button>
        <button @click="append('8')">8</button>
        <button @click="append('9')">9</button>
        <button @click="append('')"></button>
        <button @click="append('0')">0</button>
        <button @click="append('.')">.</button>
        <button @click="compute">=</button>
        <button @click="append('/')">/</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: ''
    };
  },
  methods: {
    append(char) {
      this.current += char;
    },
    clear() {
      this.current = '';
    },
    compute() {
      try {
        this.current = eval(this.current);
      } catch (e) {
        this.current = 'Error';
      }
    }
  }
};
</script>

<style>
.calculator {
  max-width: 400px;
  margin: auto;
  text-align: center;
  padding: 10px;
}
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
}
button {
  padding: 20px;
  font-size: 18px;
  border-radius: 10px;
  background: transparent;
  color: white;
  border-color: 3px solid blue;

}
input {
  width: 100%;
  padding: 20px;
  font-size: 18px;
  text-align: right;
  margin-bottom: 10px;
}
</style>