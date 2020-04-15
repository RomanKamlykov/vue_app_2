<template>
  <Test />
</template>

<script>
import Test from './components/Test.vue'

export default {
  name: 'App',
    components: {
      Test
    }
  }
</script>

<style lang="scss">
  html {
    box-sizing: border-box;
  }

  *, *::before, *::after {
    box-sizing: inherit;
  }

  body {
    background: #E5E5E5;
  }
</style>