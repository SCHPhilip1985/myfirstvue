<script setup>
import { ref } from 'vue';

   const alter = ref(0)
   console.log(alter)
   function reset() {
    alter.value=0
   }
</script>
<template>Moorbekhalle
{{ alter }}
<button @click="alter++">+</button>
<button @click="alter--">-</button>
<button @click="reset">reset</button> 

<p :class="alter<0?'minusAlter':'plusAlter'">Alter ist: {{ alter }}</p>

<input type="number" v-model="alter"/>

</template>
<style scoped>

    .minusAlter {
        background-color: red;
        color: white;
    }
    .plusAlter {
        background-color: green;
        color: white;
    }

</style>