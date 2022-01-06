<template>
  <h1>V-If / V-Else</h1>

  <p>Coche: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Potencias</p>

  <ul>
    <!-- No se visualiza correctamente 
        <li v-for="(power, index) in powers" :key="index">
      <template v-if="power < 300">
        {{ power }}
      </template>
    </li> -->

    <template v-for="(power, index) in powers" :key="index">
      <li v-if="power < 280">Urbanas: {{ power }}</li>
      <li v-else-if="power === 280">Hibrido: {{ power }}</li>
      <li v-else>Carreras: {{ power }}</li>

      <li v-if="power === 500">Exotico: {{ power }}</li>
    </template>
  </ul>
</template>

<script>
export default {
  setup() {
    const brand = "Audi";
    const model = "A4";
    const powers = [60, 80, 120, 160, 200, 280, 300, 390, 540, 500];
    return {
      brand,
      model,
      powers,
    };
  },
};
</script>

<style></style>
