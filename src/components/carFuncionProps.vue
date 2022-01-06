<template>
  <h1>Props Funcion / Coche - Composition</h1>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ modelo }}</p>
  <p>Potencia: {{ powerUp }}</p>
  <!-- ejecucion de funcion exportada -->
  <button @click="upPowerExp">Aumentar...</button>
</template>

<script>
export default {
  // Se define dentro del props, la variable que llega, con su tipo de dato y el valor por default en caso de.
  props: {
    powerUp: {
      type: Number,
      default: 20,
    },
    // exportacion de una funcion de App.vue para usarla en este componente
    upPowerExp: Function,
  },
  // Se integra el props como variable dentro de la funcion setup
  setup(props) {
    const brand = "Susuki";
    const modelo = "Ciaz";

    return {
      brand,
      modelo,
    };
  },
};
</script>

<style></style>
