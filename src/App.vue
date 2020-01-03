<template>
  <div id="app">
    <SingleElement></SingleElement>
    <CssAnimation></CssAnimation>
    <CustomTransition></CustomTransition>
    <Velocity></Velocity>
    <BetweenElements></BetweenElements>
    <ComponentTrans></ComponentTrans>
    <ListTrans></ListTrans>
    <ListMoveTrans></ListMoveTrans>
    <StaggeringListTrans></StaggeringListTrans>
    <DynamicTrans></DynamicTrans>
  </div>
</template>

<script>
import SingleElement from './components/SingleElement.vue'
import CssAnimation from './components/CssAnimation.vue'
import CustomTransition from './components/CustomTransition.vue'
import Velocity from './components/Velocity.vue'
import BetweenElements from './components/BetweenElements.vue'
import ComponentTrans from './components/ComponentTrans.vue'
import ListTrans from './components/ListTrans.vue'
import ListMoveTrans from './components/ListMoveTrans.vue'
import StaggeringListTrans from './components/StaggeringListTrans.vue'
import DynamicTrans from './components/DynamicTrans.vue'


export default {
  name: 'app',
  components: {
      SingleElement,
      CssAnimation,
      CustomTransition,
      Velocity,
      BetweenElements,
      ComponentTrans,
      ListTrans,
      ListMoveTrans,
      StaggeringListTrans,
      DynamicTrans,
  }
}
</script>

<style>

</style>
