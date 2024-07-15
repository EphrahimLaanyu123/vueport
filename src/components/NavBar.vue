<template>
  <nav>
    <div class="navs">

      <router-link
        to="/"
        class="flex items-center gap-2"
        @click="handleLinkClick"
      >
        <div class="navss">
          <img
            :src="require('@/assets/bff3254df1cf22ed74923aaa65bc2a08.jpg')"
            alt="logo"
            class="logo"
          />
          <p class="">
            Ephrahim &nbsp;
            <span class=""> | Coding Mastery</span>
          </p>
        </div>
      </router-link>

      <ul class="list">
        <li
          v-for="nav in navLinks"
          :key="nav.id"
          :class="[
            active === nav.title ? 'text-white' : 'text-secondary',
            'hover:text-white',
            'text-18px',
            'font-medium',
            'cursor-pointer'
          ]"
          @click="setActive(nav.title)"
        >
          <a :href="`#${nav.id}`">{{ nav.title }}</a>
        </li>
      </ul>

      <div class="">
        <!-- Replaced img tag with SVG -->
        <svg
          v-html="toggle ? closeIcon : menuIcon"
          @click="toggleMenu"
          class="w-28 h-28 object-contain cursor-pointer"
        ></svg>

        <div
          v-if="toggle"
          class=""
        >
          <ul class="">
            <li
              v-for="nav in navLinks"
              :key="nav.id"
              class=""
              :class="[
                active === nav.title ? 'text-white' : 'text-secondary'
              ]"
              @click="handleMenuLinkClick(nav.title)"
            >
              <a :href="`#${nav.id}`">{{ nav.title }}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue';
import { navLinks } from '../constants';

export default {
  name: 'NavBar',
  setup() {
    const active = ref('');
    const toggle = ref(false);
    const scrolled = ref(false);

    const handleScroll = () => {
      const scrollTop = window.scrollY;
      scrolled.value = scrollTop > 100;
    };

    const handleLinkClick = () => {
      active.value = '';
      window.scrollTo(0, 0);
    };

    const toggleMenu = () => {
      toggle.value = !toggle.value;
    };

    const setActive = (title) => {
      active.value = title;
    };

    const handleMenuLinkClick = (title) => {
      toggle.value = false;
      active.value = title;
    };

    // Define your SVG icons as strings
    const closeIcon = `
      <path d="M10.4099 9L16.7099 2.71C16.8982 2.5217 17.004 2.2663 17.004 2C17.004 1.7337 16.8982 1.47831 16.7099 1.29C16.5216 1.1017 16.2662 0.995911 15.9999 0.995911C15.7336 0.995911 15.4782 1.1017 15.2899 1.29L8.99994 7.59L2.70994 1.29C2.52164 1.1017 2.26624 0.995911 1.99994 0.995911C1.73364 0.995911 1.47824 1.1017 1.28994 1.29C1.10164 1.47831 0.995847 1.7337 0.995847 2C0.995847 2.2663 1.10164 2.5217 1.28994 2.71L7.58994 9L1.28994 15.29C1.19621 15.383 1.12182 15.4936 1.07105 15.6154C1.02028 15.7373 0.994141 15.868 0.994141 16C0.994141 16.132 1.02028 16.2627 1.07105 16.3846C1.12182 16.5064 1.19621 16.617 1.28994 16.71C1.3829 16.8037 1.4935 16.8781 1.61536 16.9289C1.73722 16.9797 1.86793 17.0058 1.99994 17.0058C2.13195 17.0058 2.26266 16.9797 2.38452 16.9289C2.50638 16.8781 2.61698 16.8037 2.70994 16.71L8.99994 10.41L15.2899 16.71C15.3829 16.8037 15.4935 16.8781 15.6154 16.9289C15.7372 16.9797 15.8679 17.0058 15.9999 17.0058C16.132 17.0058 16.2627 16.9797 16.3845 16.9289C16.5064 16.8781 16.617 16.8037 16.7099 16.71C16.8037 16.617 16.8781 16.5064 16.9288 16.3846C16.9796 16.2627 17.0057 16.132 17.0057 16C17.0057 15.868 16.9796 15.7373 16.9288 15.6154C16.8781 15.4936 16.8037 15.383 16.7099 15.29L10.4099 9Z" fill="#FFFFFF"/>
    `;
    
    const menuIcon = `
      <path d="M3 4H15M3 8H15M3 12H15" stroke="#FFFFFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    `;

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });

    return {
      active,
      toggle,
      scrolled,
      navLinks,
      handleLinkClick,
      toggleMenu,
      setActive,
      handleMenuLinkClick,
       // Assuming styles is imported as an object of CSS classes
      closeIcon,
      menuIcon
    };
  }
};
</script>

<style scoped>
.navs {
  display: flex;
  gap: 300px;
  margin-left: 300px;
}

.flex.items-center.gap-2 {
  display: flex;
  align-items: center;
  gap: 2px;
}

.navss {
  display: flex;
  align-items: center;
}

.list {
  display: flex;
  gap: 100px;
}

.logo {
  width: 30px;
  height: 30px;
  object-fit: contain;
}

.w-28.h-28.object-contain.cursor-pointer {
  width: 28px;
  height: 28px;
  object-fit: contain;
  cursor: pointer;
}

.text-secondary {
  color: #b0b0b0;
}

.text-18px {
  font-size: 18px;
}

.hover\:text-white:hover {
  color: #ffffff;
}

.font-medium {
  font-weight: 500;
}

.cursor-pointer {
  cursor: pointer;
}

.text-white {
  color: #ffffff;
}

.scoped-navs {
  display: flex;
  gap: 300px;
}

</style>
