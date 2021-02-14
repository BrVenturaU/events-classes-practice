<template>
  <div id="app" class="container">
    <b-row>
      <Encabezado titulo="Eventos y Clases con VueJs"/>
      <Formulario />
    </b-row>
  </div>
</template>

<script>
import Encabezado from './components/Encabezado.vue'
import Formulario from './components/Formulario.vue'

export default {
  name: 'App',
  components: {
    Encabezado,
    Formulario
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
