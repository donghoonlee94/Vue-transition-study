<template>
  <div id="app">
    <SingleElement></SingleElement>
    <CssAnimation></CssAnimation>
    <CustomTransition></CustomTransition>
  </div>
</template>

<script>
import SingleElement from './components/SingleElement.vue'
import CssAnimation from './components/CssAnimation.vue'
import CustomTransition from './components/CustomTransition.vue'

export default {
  name: 'app',
  components: {
      SingleElement,
      CssAnimation,
      CustomTransition,
  }
}
</script>

<style>

</style>
