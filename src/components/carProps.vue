<template>
  <h1>Props / Coche - Composition ! Emit en boton Disminuir</h1>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ modelo }}</p>
  <p>Potencia: {{ potencia }}</p>
  <p>Valor por Props {{ powerUp }}</p>
</template>

<script>
export default {
  // Se define dentro del props, la variable que llega, con su tipo de dato y el valor por default en caso de.
  props: {
    powerUp: {
      type: Number,
      default: 60,
    },
  },
  // se instancian las funciones exportadas mediante el Emit descrito
  emits: ["downPowerExp"],

  // Se integra el props como variable dentro de la funcion setup (1ra forma)
  // se agrega context para usar posteriormente la funcion exportada (2da forma)
  setup(props, context) {
    const brand = "Susuki";
    const modelo = "Ciaz";

    // se crea otra funcion y ahi adentro se ejecuta y se llama a la funcion exportada, mas largo  (2da forma)
    const downPowerFn = () => {
      context.emit("downPowerExp");
    };

    console.log(props.power);
    return {
      brand,
      modelo,
      // se debe por ultimo retornar la funcion creada  (2da forma)
      downPowerFn,
    };
  },
};
</script>

<style></style>
