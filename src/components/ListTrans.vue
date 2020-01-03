<template>
  <div>
    <br>
    <br>
    <h3>리스트 트렌지션</h3>
    <button v-on:click="add">Add</button>
    <button v-on:click="remove">Remove</button>
    <!-- transition-group은 디폴트 값이 span이고, tag="" 를 통해서 태그를 설정해줄 수 있음. -->
    <transition-group name="list" tag="div">
      <span v-for="item in items" v-bind:key="item" class="list-item">
        {{ item }}
      </span>
    </transition-group>
  </div>  
</template>

<script>
export default {
  data(){
    return {
      items: [1,2,3,4,5,6,7,8,9],
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
    remove() {
      this.items.splice(this.randomIndex(), 1)
    },
  }
}
</script>

<style>
  .list-item {
    display: inline-block;
    margin-right: 10px;
  }
  .list-enter-active, .list-leave-active {
    transition: all 1s;
  }
  .list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
    opacity: 0;
    transform: translateY(30px);
  }
</style>