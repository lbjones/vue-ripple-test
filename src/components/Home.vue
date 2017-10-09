<style lang="scss">
.home {
  text-align: right;
  h1 {
    color: purple;
  }
}
</style>


<template>
  <div class="home">
    <h1>Home</h1>
    <button id="b3" class="mdc-button">(MDC) static button</button>
    <ui-button>(KeenUI) static button</ui-button>
  </div>
</template>


<script>
import { MDCRipple } from '@material/ripple'
import UiButton from 'keen-ui/src/UiButton.vue'

export default {
  components: {
    UiButton
  },
  mounted () {
    MDCRipple.attachTo(document.querySelector('#b3'))
  }
}
</script>
