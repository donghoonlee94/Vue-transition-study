<template>
  <div>
    <!-- 단일 엘리먼트 / 컴포넌트 트랜지션 -->
    <button v-on:click="show = !show">
      단일 엘리먼트 / 컴포넌트 트랜지션
    </button>
    <transition 
    name="fade"
    :duration="{enter : 5, leave: 8 }">
      <p v-if="show">hello</p>
    </transition>    
  </div>
</template>

<script>
export default {
  data() {
    return {
      show : true,
    }
  },
}
</script>

<style>
  /* transition은 아래의 클래스를 제공해줌 태그 안에 name은 직접 설정이 가능하며, 뒤에 enter,leave가 따라옴*/
  /* enter -> enter-to : enter에서 to가 되기까지 이 사이에 트렌지션이 적용됨. leave는 leave에서 leave-to까지 */
  /* active는 해당 enter & leave에 대한 활성 ----> 종료 상태를 뜻함. 아래 구문 뜻은 활성화돠고 종료까지 오퍼시티 0.5초를 적용한다는 뜻*/

  
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }


/* 
  .fade-enter{
    transition: 0.5s;
    opacity: 0;
  }
  .fade-enter-to{
    transition: 0.5s;    
    opacity: 1;
  } */

   
  /* CSS 트렌지션, timing 기능을 사용할 수 있다.*/
/*   
  .fade-enter-active {
    transition: all .3s ease;
  }
  .fade-leave-active {
    transition: all .8s cubic-bezier(0.1, 0.1, 0.3, 0.8);
  }
  .fade-enter, .fade-leave-to{
    transform: translateX(10px);
    opacity: 0;
  } */


</style>