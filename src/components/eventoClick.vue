<template>
  <p>-----------------------</p>

  <h1>Evento Click</h1>

  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Potencia {{ power }}</p>
  <button @click="upPower(power)">Aumentar potencia</button>
  <button @click="downPower(power)">Disminuir potencia</button>

  <button @click="upPowerMax(power)">Aumentar potencia Maxima</button>
  <button @click="downPowerMax(power)">Disminuir potencia Maxima</button>
</template>

<script>
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
  // API de Composiciones
  setup() {
    const brand2 = "Audi";
    const model2 = "A4";
    const power2 = "70";
    let cont = 0;

    const upPowerMax = (valor) => {
      console.log("Aumentando potencia maxima " + valor);
    };

    const downPowerMax = (valor) => {
      console.log("Disminuyendo potencia maxima " + valor);
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
  methods: {
    upPower(potencia) {
      console.log("Aumentando potencia ", this.cont++);
    },
    downPower(potencia) {
      console.log("Disminuyendo potencia ", potencia--);
    },
  },
};
</script>

<style></style>
