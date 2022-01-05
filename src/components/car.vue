<template>
  <h2>coche</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ modelo }}</p>
  <p>Color: {{ color[2] }}</p>
  <p>Caballos: {{ power }} CV</p>
  <p>Precio: ${{ price }}</p>
  {{ mensaje.titulo }} - {{ mensaje.text }}

  <test />
</template>

<script>
import test from "./test.vue";
export default {
  components: {
    test,
  },
  //   data() {
  //     return {
  //       brand: "Audi",
  //       modelo: "A4",
  //       color: ["Azul", "Rojo"],
  //       price: 38000,
  //       power: 450,
  //       mensaje: {
  //         titulo: "Hola Mundo",
  //         text: "Bienvenido",
  //       },
  //     };
  //   },
  setup() {
    const brand = "Susuki";
    const modelo = "Ciaz";
    const color = ["azul", "rojo", "blanco"];
    const power = 240;
    const price = 45200;
    const mensaje = {
      titulo: "Gran auto",
      text: "aguanta de todo",
    };
    return {
      brand,
      modelo,
      color,
      power,
      price,
      mensaje,
    };
  },
};
</script>

<style></style>
