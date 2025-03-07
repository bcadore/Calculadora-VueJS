<template>
  <div class="container">
    <div class="text-center my-3">
      <h1 class="m-0">Calculadora Aritmética EBAC - VueJS</h1>
    </div>

    <div class="d-flex justify-content-evenly mb-3">
      <input
        class="form-control w-25"
        type="number"
        v-model.number="num1"
      />
      <select class="form-select mx-3 w-25" v-model="operacao">
        <option selected>Selecione uma Operação</option>
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">x</option>
        <option value="divisao">/</option>
      </select>
      <input
        class="form-control w-25"
        type="number"
        v-model.number="num2"
      />
    </div>
    <div class="text-center mb-3">
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: "Selecione uma Operação",
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case "soma":
          return this.num1 + this.num2;
        case "subtracao":
          return this.num1 - this.num2;
        case "multiplicacao":
          return this.num1 * this.num2;
        case "divisao":
          return this.num2 !== 0
            ? this.num1 / this.num2
            : "Erro. Divisão por zero não é permitido!";
        default:
          return 0;
      }
    },
  },
};
</script>

<style></style>
