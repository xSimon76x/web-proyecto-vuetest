<template>
  <p>-----------------------</p>

  <h1>Evento Click con Binding</h1>

  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Potencia: {{ power2 }}</p>
  <!-- Incrementar de 50 en 50 con api de opciones-->
  <button @click="upPower(50)">Aumentar potencia</button>
  <!-- Disminuir con api de opciones-->
  <button @click="downPower()">Disminuir potencia</button>

  <!-- Incrementar de 10 en 10 con api de composiciones-->
  <button @click="upPowerMax(10)">Aumentar potencia Maxima</button>
  <!-- Disminuir con api de composiciones-->
  <button @click="downPowerMax()">Disminuir potencia Maxima</button>
</template>

<script>
import { ref } from "vue";

export default {
  // API de Opciones
  data() {
    return {
      brand: "Seat",
      model: "Leon",
      power: 50,
      cont: 0,
    };
  },
  methods: {
    upPower(valor) {
      console.log("Aumentando potencia ", (this.power = this.power + valor));
    },
    downPower() {
      console.log("Disminuyendo potencia ", this.power--);
    },
  },

  // API de Composiciones
  setup() {
    const brand2 = "Audi";
    const model2 = "A4";
    let power2 = ref(70);
    let cont = 0;

    const upPowerMax = (valu) => {
      // mal sintaxis power2++;
      power2.value = power2.value + valu;
      console.log("Aumentando potencia maxima " + power2.value);
    };

    const downPowerMax = () => {
      power2.value--;
      console.log("Disminuyendo potencia maxima " + power2.value);
    };

    return {
      brand2,
      model2,
      power2,
      upPowerMax,
      downPowerMax,
      cont,
    };
  },
};
</script>

<style></style>
