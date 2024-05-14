<script>
export default {
  data() {
    return {
      colorFondo: "darkgreen",
      colorTexto: "white",
      mostrar: true,
      borde: 70,
      contenido: "Awesome Vue.js",
      tipografia: "cursive",
      tamanio: "20",
      opaco: true,
      options: [
        "cursive",
        "italic",
        "sans-serif",
        "fantasy",
      ]
    }
  }
}
</script>

<template>

  <div class="wrapper">
    <div class="form">
      <div class="campo">
        <label for="colorFondo">Color de fondo</label>
        <input v-model="colorFondo" type="text" name="colorFondo" id="colorFondo">
      </div>
      
      <div class="campo">
        <label for="colorTexto">Color de texto</label>
        <input v-model="colorTexto" type="text" name="colorTexto" id="colorTexto">
      </div>
      
      <div class="campo--checkbox">
        <label for="mostrar">Mostrar texto</label>
        <input v-model="mostrar" type="checkbox" name="mostrar" id="mostrar">
      </div>

      <div class="campo">
        <label for="borde">Borde</label>
        <input v-model="borde" type="range" name="borde" id="borde">
      </div>

      <div class="campo">
        <label for="contenido">Contenido textual</label>
        <textarea v-model="contenido" name="contenido" id="contenido" rows="5"></textarea>
      </div>

      <div class="campo">
        <label for="tipografia">Tipografía</label>
        <select v-model="tipografia" name="tipografia" id="tipografia">
          <option v-for="option in options" :value="option">{{ option }}</option>
        </select>
      </div>
      
      <div class="campo--checkbox">
        <label for="opaco">Opaco</label>
        <input v-model="opaco" type="checkbox" name="opaco" id="opaco">
      </div>

      <div class="campo">
        <p>Tamaño de letra</p>

        <div class="campo--radio">
          <div class="radio">
            <input type="radio" v-model="tamanio" name="tamanio" id="pequenio" value="10">
            <label for="pequenio">Pequeño</label>
          </div>

          <div class="radio">
            <input type="radio" v-model="tamanio" name="tamanio" id="mediano" value="20">
            <label for="mediano">Mediano</label>
          </div>

          <div class="radio">
            <input type="radio" v-model="tamanio" name="tamanio" id="Grande" value="30">
            <label for="Grande">Grande</label>
          </div>
        </div>
      </div>
    </div>
    
    <div 
      class="contenido"
      :class="{
          opacidad: opaco
      }"
      :style="{
        backgroundColor: colorFondo,
        color: colorTexto,
        borderRadius: `${borde}px`,
        fontFamily: tipografia,
        fontSize: `${tamanio}px`,
      }"
      >
      <p
        v-show="mostrar"
      >{{ contenido }}</p>
    </div>
  </div>

</template>

<style scoped>

.opacidad {
  opacity: .5;
}

.wrapper {
  display: flex;
  align-items: center;
}

.form {
  background: rgb(48, 85, 87);
  padding: 2rem;
  color: #FFF;
  flex-basis: 50%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contenido {
  margin: 0 auto;
  flex-basis: 20rem;
  height: 20rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: red;
}

.campo {
  display: flex;
  flex-direction: column;
}

.campo--radio {
  display: flex;
  gap: .3rem;
}

p {
  margin: 0;
}

</style>
