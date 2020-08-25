<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    {{a}}
    <button @click="add">add</button>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import {reactive, ref, effect} from '@vue/reactivity';
export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // },
  setup() {
    let a = ref(0);
    const obj = reactive({ count: 0 })
    console.log(obj);
    let dummy = a.value;
    effect(() => {
      dummy = a.value;
      console.log(dummy);
    });
    function add() {
      a.value++;
    }
    return {
      a,
      add
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
