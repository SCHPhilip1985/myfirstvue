<script setup>
import { reactive, ref } from 'vue'; 
import MyComponent from "./components/MyComponent.vue"
import MyInput from "./components/MyInput.vue"
import MyInput2 from './components/MyInput2.vue';
import Filme from './components/Filme.vue';

const counter = reactive ({count: 0}) 
const message = ref('Hello World!')
</script>

<template>
  <!-- <h1>{{ message }}</h1>
  <button @click="counter.count++">+</button>
  <button @click="counter.count--">-</button>
  <button @click="counter.count=0">reset</button>

  <p :class="counter.count<0?'minusCount':'positiveCount'">Count is: {{ counter.count }}</p>

<MyComponent /> -->
<!-- <MyInput /> -->
<!-- <MyInput2 /> -->
<Filme />
</template>

<style scoped>
.minusCount {
  color: red;
}
.positiveCount{
  color:green;
}

</style>
