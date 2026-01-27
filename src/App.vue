
<script setup>
import { ref } from "vue";
import Counter from "./components/counter.vue";

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
  <h1>Hello, {{ Name }}</h1>
  <p>Address: {{ Address }}</p>
  <h1>Oyy... <span v-text="Name"></span> !!!</h1>
  <h2 v-html="html"></h2>

  <br><br>
  <br>

  <h3 v-if="active">Hashao Mahmud !</h3>
  <h3 v-else>Mahmud, hashi kothay?</h3>
  <button v-on:click="changeName">Change-Name</button>

  <br><br>
  <br><br>
  <ol>
    <li v-for="(student , i) in Students" :key="i">{{ student }}</li>
  </ol>
  <br><br>
  <br>

  <Counter/>
  <br>
  <br>
  <Counter/>
</template>


<style scoped>

</style>
