<template>
  <h1>{{ titulo }}</h1>
  <input type="number" v-model="primerNumero" />
  <input type="number" v-model="segundoNumero" />
  <br />
  <button @click="sumar">+</button>
  <button @click="restar">-</button>
  <button @click="multiplicar">*</button>
  <p>{{ resultado }}</p>
</template>

<script>
import { computed } from "@vue/reactivity";
export default {
  name: "Calculadora",
  props: {
    uno: {
      type: Number,
      default: 0,
    },
    dos: {
      type: Number,
      default: 0,
    },
    messResultado: {
      type: String,
      default: "",
    },
    titulo: {
      type: String,
      default: "Calculadora",
    },
  },
  data() {
    return {
      primerNumero: this.uno,
      segundoNumero: this.dos,
      resultado: this.messResultado,
    };
  },
  methods: {
    sumar() {
      this.resultado =
        "La suma es: " + (this.primerNumero + this.segundoNumero);
    },
    restar() {
      this.resultado =
        "La resta es: " + (this.primerNumero - this.segundoNumero);
    },
    multiplicar() {
      this.resultado =
        "La multiplicacion es: " + this.primerNumero * this.segundoNumero;
    },
  },
  computed: {},
};
</script>

<style scoped>
button {
  background-color: forestgreen;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  padding: 5px 15px;
  margin: 0px 10px;
}

button:hover {
  background-color: greenyellow;
}

input {
  border-radius: 5px;
  padding: 5px 15px;
  margin: 10px 10px;
}
</style>