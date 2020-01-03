<template>
  <div>
    <br>
    <h3>엘리먼트 간 트랜지션</h3>
    <transition>
      <button v-bind:key="isEditing" @click="isEditing = !isEditing">
        {{ isEditing ? 'Save' : 'Edit' }}
      </button>
    </transition>
    <br>
    <br>
    <!-- in-out: 처음에는 새로운 엘리먼트가 트랜지션되고, 완료되면 현재 엘리먼트가 트랜지션됩니다. -->
    <!-- out-in: 현재 엘리먼트가 먼저 트랜지션되고, 완료되면 새로운 요소가 바뀝니다 -->
    <transition name="fade" mode="out-in">
      <button v-bind:key="isSaved" @click="isSaved = !isSaved">
        {{ isSaved ? 'Save' : 'Edit' }}
      </button>
    </transition>    
    <br>
    <br>
    <transition name="fade" mode="in-out">
      <button v-bind:key="isInout" @click="isInout = !isInout">
        {{ isInout ? 'Save' : 'Edit' }}
      </button>
    </transition>    
    <br>
    <br>
    <transition name="slide-fade">
      <button v-bind:key="isSlide" @click="isSlide = !isSlide" class="slide-fade">
        {{ isSlide ? 'Save' : 'Edit' }}
      </button>
    </transition>    
  </div>
</template>

<script>
export default {
  data() {
    return {
      isEditing : true,
      isSaved : true,
      isInout : true,
      isSlide : true,
    }
  },
}
</script>

<style>
.slide-fade{
  position:absolute;
}
.slide-fade-enter-active, .slide-fade-leave-active{
  transition: all 1.0s;
  opacity: 1;
}

.slide-fade-enter, .slide-fade-leave-to{
  transform: translateX(31px);
  opacity:0;
}
</style>