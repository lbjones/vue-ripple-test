<style lang="scss" scoped>
.home {
  text-align: right;
  h1 {
    color: red;
  }
}
</style>


<template>
  <div class="home">
    <h1>Home</h1>
    <button id="b3" class="mdc-button">(MDC) static home button</button>
    <ui-button>(KeenUI) static home button</ui-button>
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
    this.ripple = MDCRipple.attachTo(document.querySelector('#b3'))
    console.log('mounted #b3')
  },
  beforeDestroy () {
    this.ripple.destroy()
    console.log('destroyed #b3')
  }
}
</script>
