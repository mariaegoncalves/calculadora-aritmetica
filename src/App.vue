<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model="numero1" placeholder="Número 1" />
      <select v-model="operacao" @change="calcular">
        <option value="">Escolha uma operação</option>
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model="numero2" placeholder="Número 2" />
    </div>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '',
      resultado: 0,
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case '+':
          this.resultado = Number(this.numero1) + Number(this.numero2);
          break;
        case '-':
          this.resultado = Number(this.numero1) - Number(this.numero2);
          break;
        case '*':
          this.resultado = Number(this.numero1) * Number(this.numero2);
          break;
        case '/':
          this.resultado = Number(this.numero1) / Number(this.numero2);
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
input {
  margin: 5px;
}
</style>
