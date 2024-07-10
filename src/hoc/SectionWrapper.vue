<template>
  <motion-section
    v-bind:variants="staggerContainer()"
    initial="hidden"
    whileInView="show"
    viewport="{ once: true, amount: 0.25 }"
    :class="{ [styles.padding]: true, 'max-w-7xl mx-auto relative z-0': true }"
  >
    <span class="hash-span" :id="idName">&nbsp;</span>
    <slot />
  </motion-section>
</template>

<script>
import { defineComponent } from 'vue';
import { motion } from 'framer-motion'; // Assuming you're using Framer Motion in Vue

export default defineComponent({
  props: {
    idName: String, // Prop to receive the ID name for the hash span
  },
  setup(props) {
    return {
      staggerContainer, // Assuming you have the staggerContainer function defined elsewhere
    };
  },
});
</script>

<style scoped>
/* Add your styling here, referencing classes from the template */
</style>
