<style lang="scss">
.login {
  text-align: right;
  h1 {
    color: purple;
  }
}
</style>


<template>
  <div class="login">
    <h1>Login</h1>
    <button id="b4" class="mdc-button">(MDC) static button</button>
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
    MDCRipple.attachTo(document.querySelector('#b4'))
  }
}
</script>
