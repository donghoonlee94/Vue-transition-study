<template>
  <div>
    <br>
    <br>
    <input v-model="query">
    <transition-group
      name="staggered-fade"
      tag="ul"
      v-bind:css="false"
      v-on:before-enter="beforeEnter"
      v-on:enter="enter"
      v-on:leave="leave"
    >
      <li
        v-for="(item, index) in computedList"
        v-bind:key="item.msg"
        v-bind:data-index="index"
      >{{ item.msg }}</li>

    </transition-group>
  </div>  
</template>

<script>
import Velocity from 'velocity-animate';

export default {
  data() {
    return {
      query: '',
      list: [
        { msg: 'Bruce Lee' },
        { msg: 'Jackie Chan' },
        { msg: 'Chuck Norris' },
        { msg: 'Jet Li' },
        { msg: 'Kung Fury' }
      ]
    }
  },
  computed: {
    // list.msg의 소문자의 값 중에서, 입력 받는 query값의 소문자와 일치하는 값이 있으면 1 이상을 반환, 없으면 -1을 반환. !== -1 은 일치하는 경우를 뜻함.
    // 위 내용을 filter로 감쌌기 때문에, 일치하는 값이 있을 경우 해당 글자를 포함하는 value 값을 되돌려줌.
    computedList: function () {
      var vm = this
      return this.list.filter(item => {
        return item.msg.toLowerCase().indexOf(vm.query.toLowerCase()) !== -1
      })
    }
  },
  methods: {
    beforeEnter: function (el) {
      el.style.opacity = 0
      el.style.height = 0
    },
    enter: function (el, done) {
      var delay = el.dataset.index * 150
      setTimeout(function () {
        Velocity(
          el,
          { opacity: 1, height: '1.6em' },
          { complete: done }
        )
      }, delay)
    },
    leave: function (el, done) {
      var delay = el.dataset.index * 150
      setTimeout(function () {
        Velocity(
          el,
          { opacity: 0, height: 0 },
          { complete: done }
        )
      }, delay)
    }
  }
}
</script>

<style>

</style>