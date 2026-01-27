<template>
    
  <!-- Counter -->
  <div class="counter">
    <h2>Counter: {{ count }}</h2>

    <button @click="decrease">−</button>
    <button @click="increase">+</button>
    <button @click="reset">Reset</button>
  </div>

</template>


<script setup>
import { ref } from 'vue';


  let count = ref(0);
  function increase(){
    count.value++;
  }
  
function decrease() {
  count.value--;
}

function reset() {
  count.value = 0;
}
</script>

<style>

</style>