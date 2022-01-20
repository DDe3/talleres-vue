<template>
  <h2>{{ titulo }}</h2>
  <p>{{ contador }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>
  <button @click="aumentarContador">Aumentar</button>
  <button @click="restarContador">Disminuir</button>
</template>

<script>
import { computed } from "@vue/reactivity";
export default {
  name: "Contador",
  //props: ["titulo", "valor_inicial"],
  props: {
    titulo: {
        type: String,
        default: "Forma mas eficiente de declarar props",
        required: false
    },
    valor_inicial: {
        type: Number,
        default: 0,
        required: false,
        validator(value) { 
            return value>=0
        }
    } 
  },
  data() {
    return {
      contador: this.valor_inicial,
    };
  },
  methods: {
    obtenerCuadrado() {
      console.log("Se calcula el cuadrado");
      return this.contador * this.contador;
    },
    aumentarContador() {
      this.contador++;
    },
    restarContador() {
      this.contador--;
    },
  },
  computed: {
    obtenerCuadradoComputado() {
      console.log("Se calcula el cuadrado");
      return this.contador * this.contador;
    },

    mostrarTitulo() {
      /*
            if (this.titulo==undefined) {
                return "Contador por defecto"
            } else {
                return this.titulo
            }
        }
        */
      return this.valor_inicial != undefined
        ? "Contador por defecto"
        : this.titulo;
    },
  },
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
</style>
