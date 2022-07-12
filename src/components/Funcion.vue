<template>
  <section class="src-components-funcion">
    <div>
      <span>Color: </span
      ><input type="text" v-model="color" placeholder="Color de letra" />
      <span>Fondo: </span
      ><input type="text" v-model="background" placeholder="Color de fondo" />
      <span>Size: </span
      ><input type="text" v-model="size" placeholder="Tamanio de letra" />

      <hr />
      <br />
      <span>Texto: </span
      ><input
        :style="modificarEstilos"
        type="text"
        v-model="texto"
        placeholder="Escribí algo acá"
      />
      <br />
      <div v-if="texto.length">
        <p>Cantidad palabras = {{ contarPalabras }}</p>
      </div>
    </div>
    <br />
    <hr />

    <div id="table">
      <table>
        <tr>
          <th scope="col">Número de pregunta</th>
          <th scope="col">Respuestas</th>
        </tr>
        <tr>
          <td>1</td>
          <td>B</td>
        </tr>
        <tr>
          <td>2</td>
          <td>C</td>
        </tr>
        <tr>
          <td>3</td>
          <td>B</td>
        </tr>
        <tr>
          <td>4</td>
          <td>D</td>
        </tr>
        <tr>
          <td>5</td>
          <td>D</td>
        </tr>
      </table>
    </div>
  </section>
</template>

<script>
export default {
  name: "src-components-funcion",
  data() {
    return {
      texto: [],
      color: "",
      background: "",
      size: "",
    };
  },
  computed: {
    contarPalabras() {
      let palabrasSinEspacios = this.texto.trim();
      let arrayDePalabras = palabrasSinEspacios.split(" ");
      return arrayDePalabras.length;
    },
    modificarEstilos() {
      return {
        color: this.color,
        background: this.background,
        fontSize: this.size,
      };
    },
  },
};
</script>

<style scoped lang="css">
</style>