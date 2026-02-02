
<script setup>
import { ref } from "vue";
import Counter from "./components/Counter.vue";
import { RouterView } from "vue-router";
// import Main from "./layouts/main.vue";
import Main from "./layouts/main.vue";

  let Name="Masud";
  let Address= "Segun Bagicha, Dhaka";
  let html="<span>Hello BD</span>";

  let active =ref(false);
  const changeName = ()=>{
    active.value = !active.value;
  }

  // Array
  let Students = ["Jamal","Kamal","Tomal","Rasel", "Arif"];
  
</script>


<template>
  <Main/>
</template>


<style scoped>

</style>
