<style lang="scss" scoped>
.login {
  text-align: right;
  h1 {
    color: green;
  }
}
</style>


<template>
  <div class="login">
    <h1>Login</h1>
    <button id="b4" class="mdc-button">(MDC) static login button</button>
    <ui-button>(KeenUI) static login button</ui-button>
  </div>
</template>


<script>
import { MDCRipple } from '@material/ripple'
import UiButton from 'keen-ui/src/UiButton.vue'

export default {
  data () {
    return {
      ripple: null
    }
  },
  components: {
    UiButton
  },
  mounted () {
    this.ripple = new MDCRipple(document.querySelector('#b4'))
    console.log('mounted #b4')
  },
  beforeDestroy () {
    this.ripple.destroy()
    console.log('destroyed #b4')
  }
}
</script>
