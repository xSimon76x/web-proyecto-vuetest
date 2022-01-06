<template>
  <h2>coche</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ modelo }}</p>
  <p>
    Color:
    <!-- <span v-for="(color, index) in colors" :key="index">
      {{ index }}: {{ color }}
    </span> -->
    <ul>
      <li v-for="(color, index) in colors" :key="index">
         {{ index }}: {{ color }}
      </li>
    </ul>
  </p>
  <p>Caballos: {{ power }} CV</p>
  <p>Precio: ${{ price }}</p>
  {{ mensaje.titulo }} - {{ mensaje.text }}
  <!-- Componentes -->
  <test />
  <vIf />
  <click />
</template>

<script>
import test from "./test.vue";
import vIf from "./vIf-vElse.vue"
import click from "./eventoClick.vue"
export default {
  components: {
    test,
    vIf,
    click
  },

  setup() {
    const brand = "Susuki";
    const modelo = "Ciaz";
    const colors = ["azul", "rojo", "blanco"];
    const power = 240;
    const price = 45200;
    const mensaje = {
      titulo: "Gran auto",
      text: "aguanta de todo",
    };
    return {
      brand,
      modelo,
      colors,
      power,
      price,
      mensaje,
    };
  },
};
</script>

<style></style>
