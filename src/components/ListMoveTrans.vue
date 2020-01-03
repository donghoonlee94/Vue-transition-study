<template>
  <div class="demo">
    <br>
    <br>
    <!-- 위치의 변화를 표헌할 수 있음. move클래스를 감지한다. 네임 + move   -->
    <h3>리스트 이동 트렌지션</h3>
    <button v-on:click="shuffle">Shuffle</button>
    <transition-group name="flip-list" tag="ul">
      <li v-for="item in items" v-bind:key="item">
        {{ item }}
      </li>
    </transition-group>
    <br>
    <br>
    <div class="demo">
      <button v-on:click="anotherShuffle">Shuffle</button>
      <button v-on:click="anotherAdd">Add</button>
      <button v-on:click="anotherRemove">Remove</button>
      <transition-group name="list-complete" tag="p">
        <span
          v-for="item in anotherItems"
          v-bind:key="item"
          class="list-complete-item"
        >
          {{ item }}
        </span>
      </transition-group>
    </div>    
  </div>
</template>

<script>
import _shuffle from 'lodash/_baseShuffle'
export default {
  data() {
    return {
      items: [1,2,3,4,5,6,7,8,9],
      anotherItems : [1,2,3,4,5,6,7,8,9],
      nextNum: 10
    }
  },
  methods: {
    randomIndex() {
      return Math.floor(Math.random() * this.items.length)
    },
    add() {
      this.items.splice(this.randomIndex(), 0, this.nextNum++)
    },
    anotherAdd() {
      this.anotherItems.splice(this.randomIndex(), 0, this.nextNum++)
    },    
    remove() {
      this.items.splice(this.randomIndex(), 1)
    },    
    anotherRemove() {
      this.anotherItems.splice(this.randomIndex(), 1)
    },      
    shuffle() {
      this.items = _shuffle(this.items)
    },
    anotherShuffle() {
      this.anotherItems = _shuffle(this.anotherItems)
    }    
  }
}
</script>

<style>
/* display:inline은 FLIP 트렌지션을 작동시키지 않음, FLIP 트렌지션은 inline-block 혹은 flex 요소에 배치할 수 있음.  */
.flip-list-move {
  transition: all 1s;
}

.list-complete-item {
  transition: all 1s;
  display: inline-block;
  margin-right: 10px;
}
.list-complete-enter, .list-complete-leave-to
/* .list-complete-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(30px);
}
.list-complete-leave-active {
  position: absolute;
}
</style>