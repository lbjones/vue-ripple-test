<style lang="scss">
@import "@material/button/mdc-button";
@import "@material/toolbar/mdc-toolbar";

button, a {
  margin-right: 1rem;
}
.mdc-button {
  background-color: #ccc !important;
}
</style>


<template>
  <div id="app">
    <header ref="toolbar" class="mdc-toolbar">
      <div class="mdc-toolbar__row">
        <section class="mdc-toolbar__section mdc-toolbar__section--align-start">
          Logo
        </section>
        <section class="mdc-toolbar__section mdc-toolbar__section--align-end mdc-toolbar__section--shrink-to-fit">
          <router-link id="b1" class="mdc-button" to="/">(MDC) Home</router-link>
          <router-link id="b2" class="mdc-button" to="/login">(MDC) Login</router-link>
          <ui-button @click="goto('/')">(KeenUI) Home</ui-button>
          <ui-button @click="goto('/login')">(KeenUI) Login</ui-button>
        </section>
      </div>
    </header>
    <router-view/>
  </div>
</template>

<script>
import { MDCToolbar } from '@material/toolbar'
import { MDCRipple } from '@material/ripple'
import UiButton from 'keen-ui/src/UiButton.vue'

export default {
  data () {
    return {
      ripple1: null,
      ripple2: null
    }
  },
  components: {
    MDCToolbar, UiButton
  },
  mounted () {
    this.ripple1 = new MDCRipple(document.querySelector('#b1'))
    this.ripple2 = new MDCRipple(document.querySelector('#b2'))
    console.log('mounted #b1, #b2')
  },
  methods: {
    goto (loc) {
      this.$router.push(loc)
    }
  },
  beforeDestroy () {
    this.ripple1.destroy()
    this.ripple2.destroy()
    console.log('destroyed #b1 #b2')
  }
}
</script>
