<template>
  <h1>Vue JS</h1>
  <p>nuevo parrafo</p>
  <cardComponent />
  <!-- Sin los dos puntos, el prop enviara el texto -->
  <!-- Debe ser con los puntos para enviar al componente hijo Funciones, arreglos, variables, objetos -->
  <carProp :powerUp="powerUp" />
  <!-- exportacion de funcion y variable al componente  carFuncion -->
  <!-- exportacion de funcion con un "Emit -  menos 'limpia' " -->
  <carFuncion
    :upPowerExp="upPowerExp"
    :powerUp="powerUp"
    @downPowerExp="downPowerExp"
  />
</template>

<script>
import { ref } from "vue";
import cardComponent from "./components/car.vue";
import carProp from "./components/carProps.vue";
import carFuncion from "./components/carFuncionProps.vue";

export default {
  components: {
    cardComponent,
    carProp,
    carFuncion,
  },
  setup() {
    let powerUp = ref(70);

    const upPowerExp = () => {
      powerUp.value++;
      console.log("Aumentando en ....", powerUp.value);
    };

    const downPowerExp = () => {
      powerUp.value--;
    };
    return {
      powerUp,
      upPowerExp,
      downPowerExp,
    };
  },
};
</script>

<style></style>
