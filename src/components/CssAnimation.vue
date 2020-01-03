<template>
  <div>
    <button @click="show = !show">CSS 애니메이션 키</button>
    <!-- appear 속성은 초기 렌더링 시 작동하게 하는 속성, appear-class="custom-appear-class" 등으로 사용자 정의 클래스 지정 가능 -->
    <!-- v-on:before-appear="customBeforeAppearHook" 처럼 사용자 정의 Javascript 훅도 사용 가능함 -->
    <transition name="bounce" appear>
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