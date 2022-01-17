<template>
  <h2>Contador</h2>
  <p>{{contador}} <sup>2</sup> = {{obtenerCuadradoComputado}}</p>
  <button v-on:click="aumentarContador">Aumentar</button>
</template>

<script>
import { computed } from '@vue/reactivity'
export default {
    name: "Contador",
    data() {
        return {
            contador: 5,
        }
    },
    methods: {
        obtenerCuadrado() {
            console.log("Se calcula el cuadrado")
            return this.contador*this.contador
        },
        aumentarContador() {
            this.contador++
        }
    },
    computed: {
        obtenerCuadradoComputado() {
            console.log("Se calcula el cuadrado")
            return this.contador*this.contador
        }
    }

}
</script>

<style>

</style>
