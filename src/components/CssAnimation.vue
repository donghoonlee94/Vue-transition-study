<template>
  <div>
    <button @click="show = !show">CSS 애니메이션 키</button>
    <transition name="bounce">
      <p v-if="show">가나다라마바사아자차카타파하삐리뽕뾰로뽕</p>
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
  .bounce-enter-active {
    animation: bounce-in .5s;
  }
  .bounce-leave-active {
    animation: bounce-in reverse .5s;
  }
  
  /* CSS 애니메이션 */
  @keyframes bounce-in {
    0% {
      transform: scale(0);
    }
    50% {
      transform: scale(1.5);
    }
    100% {
      transform: scale(1);
    }
  }
</style>