<template>
  <div>
    <br>
    <button @click="show = !show">
      사용자 지정 트렌지션 
    </button>
    <!-- enter일 때 에니메이트, leave 일 때 에니메이트, -->
    <transition
      name="custom-classes-transition"
      enter-active-class="animated tada"
      leave-active-class="animated bounceOutRight"
    >
      <p v-if="show">안녕하세요</p>
    </transition>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      show: true,
    }
  },
}
</script>

<style>
  @import '../css/Animate.css';
</style>