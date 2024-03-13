<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <input v-model.number="numero1" type="number" placeholder="Número 1" />
    <input v-model.number="numero2" type="number" placeholder="Número 2" />

    <select v-model="operacao">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>

    <div>Resultado: {{ resultado }}</div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0,
    };
  },
  watch: {
    numero1: 'calcular',
    numero2: 'calcular',
    operacao: 'calcular',
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = this.numero1 + this.numero2;
          break;
        case 'subtracao':
          this.resultado = this.numero1 - this.numero2;
          break;
        case 'multiplicacao':
          this.resultado = this.numero1 * this.numero2;
          break;
        case 'divisao':
          this.resultado = this.numero1 / this.numero2;
          break;
      }
    },
  },
  mounted() {
    this.calcular();
  },
};
</script>

<style>
/* Adicione qualquer estilo que desejar aqui */
</style>
