<template>
  <div>
      <br>
      <br>
      <br>
      <h3>컴포넌트 트렌지션</h3>
      <input type="radio" value="componentA" id="a" v-model="view">
      <label for="a">ComponentA</label>
      <input type="radio" value="componentB" id="b" v-model="view">
      <label for="b">ComponentB</label>    
      <transition name="component-fade" mode="out-in">
        <component :is="view"></component>
      </transition>    
  </div>
</template>

<script>
import ComponentA from './ComponentTransA.vue'
import ComponentB from './ComponentTransB.vue'

export default {
  data() {
    return {
      view: ''
    }
  },  
  components: {
    ComponentA,
    ComponentB,
  }
}
</script>

<style>
.component-fade-enter-active, .component-fade-leave-active {
  transition: opacity .3s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>