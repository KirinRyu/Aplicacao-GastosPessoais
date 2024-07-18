<template>
  <div class="base-spinner fa-3x" v-if="visible">
    <i class="fa fa-circle-notch fa-spin"></i>
  </div>
</template>

<script>
import eventBus from './eventBus.js'

export default {

  data () {
    return {
      visible: false
    }
  },
  created () {
    eventBus.on('Spinner::show', this.setSpinner)
    eventBus.on('Spinner::hide', this.setSpinner)
  },
  methods: {
    setSpinner () {
      this.visible = !this.visible
    }
  }
}

</script>

<style lang="scss" scoped>
  @import '../../assets/scss/variable';

.base-spinner {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  z-index: 10000000;
  width: 100vw;
  height: 100vh;
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: $dark-medium;
  color: $featured;
}
</style>
