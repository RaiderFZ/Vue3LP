<script setup lang="ts">
import Counter from './components/Counter.vue';
import ToDoList from './components/ToDoList.vue';
import CartList from './components/CartList.vue';
import LiveMount from './components/LiveMount.vue';
</script>

<template>
  <LiveMount/>


  <Counter send="Hello Vue3" />
  <ToDoList/>
  <CartList/>
</template>

<style scoped>

</style>
