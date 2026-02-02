<template>
    <Header/>

    <div class="container">
        <Sidebar/>
        <RouterView/>
    </div>
    <Footer/>

    
</template>

<script setup>
import Footer from './Footer.vue';
import Header from './Header.vue';
import Sidebar from './Sidebar.vue';

</script>



<style> 

</style>