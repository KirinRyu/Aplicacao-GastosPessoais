<template>
  <div>
    <base-spinner></base-spinner>
    <!-- <router-view/> -->
     <button @click="mostrarSpinner()">
      Mostrar Spinner
     </button>
  </div>
</template>

<script>
import BaseSpinner from './components/global/BaseSpinner.vue'
import eventBus from './components/global/eventBus'

export default {
  name: 'App',
  components: {
    BaseSpinner
  },
  methods: {
    mostrarSpinner () {
      console.log('clicado')
      eventBus.emit('Spinner::show')
    }
  }
}
</script>

<style lang="scss">

</style>
