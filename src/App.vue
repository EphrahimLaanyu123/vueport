<template>
  <div>
    <Navbar />

    <Hero />

    <About/>

    <Experience/>

    <Works/>

    <CreatePost/>





    <router-view />
  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue'; 
import Experience from './components/Experience.vue'; 
import Works from './components/Works.vue'; 
import CreatePost from './components/Contact.vue'; 

export default {
  components: {
    Navbar,
    Hero,
    About,
    Experience,
    Works,
    CreatePost

  },
};
</script>

<style>

</style>


