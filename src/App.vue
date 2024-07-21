<template>
  <div class="app">
    <Navbar />

    <Hero />

    <About />

    <Experience />

    <Works />

    <CreatePost />

    <router-view />
  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Experience from './components/Experience.vue';
import Works from './components/Works.vue';
import CreatePost from './components/Contact.vue'; // Assuming Contact is the intended component

export default {
  components: {
    Navbar,
    Hero,
    About,
    Experience,
    Works,
    CreatePost,
  },
};
</script>

<style scoped>
/* Base styles for mobile-first approach */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  /* Add more generic fallback fonts if needed */
  font-size: 16px; /* Base font size */
  line-height: 1.5; /* Adjust leading for readability */
}

/* Breakpoint mixin for easier media query usage */
@mixin breakpoint($min) {
  @media (min-width: $min) {
    @content;
  }
}

/* Specific styles for different components or sections (replace with your actual styles) */
.navbar {
  @include breakpoint(768px) {
    /* Adjust navbar styles for larger screens */
  }
}

.hero {
  /* Add styles for hero section */
}

/* ... styles for About, Experience, Works, CreatePost, etc. ... */

/* Example responsive layout for Hero section */
.hero {
  padding: 2rem;

  @include breakpoint(768px) {
    padding: 3rem;
  }

  @include breakpoint(1024px) {
    padding: 4rem;
  }
}
</style>
