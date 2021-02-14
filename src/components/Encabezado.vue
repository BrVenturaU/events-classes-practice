<template>
    <b-row class="mx-auto">
        <b-col cols="12" class="mb-3">
            <img alt="App logo" src="@/assets/logo.png">
            <h1>{{ titulo }}</h1>
            <small>Si puedes hacer esto con tus manos, tienes un mundo por delante con tu creatividad.</small>
        </b-col>
    </b-row>
</template>

<script>
export default {
  name: 'Encabezado',
  props: {
    titulo: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>