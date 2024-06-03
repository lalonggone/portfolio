<template>
  <div id="app">
    <Header :isDarkMode="isDarkMode" @update:isDarkMode="toggleTheme" />
      <section id="hero">
        <HeroSection />
      </section>
      <section id="projects">
        <ProjectsSection />
      </section>
      <section id="about">
        <AboutSection />
      </section>
      <section id="contact">
        <ContactSection />
      </section>
    <Footer />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed, watch, onMounted } from 'vue';
import Header from './components/NavBar.vue';
import Footer from './components/Footer.vue';
import HeroSection from './components/HeroSection.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import AboutSection from './components/AboutSection.vue';
import ContactSection from './components/ContactSection.vue';

export default defineComponent({
  name: 'App',
  components: {
    Header,
    Footer,
    HeroSection,
    ProjectsSection,
    AboutSection,
    ContactSection
  },
  setup() {
    const isDarkMode = ref(true); 

    const toggleTheme = (isDark: boolean) => {
      isDarkMode.value = isDark;
    };

    const themeClass = computed(() => (isDarkMode.value ? 'dark-mode' : 'light-mode'));

    watch(themeClass, (newClass, oldClass) => {
      document.body.classList.remove(oldClass);
      document.body.classList.add(newClass);
    });

    onMounted(() => {
      document.body.classList.add(themeClass.value);
    });

    return { isDarkMode, toggleTheme, themeClass };
  }
});
</script>

<style>
html {
  scroll-behavior: smooth;
}

#app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px 20px;
  font-family: Montserrat, sans-serif;
  color: var(--text-color);
  transition: color 0.5s;
}

body {
  background-color: var(--bg-color);
}

/* header, footer {
  background-color: var(--header-bg-color);
  color: var(--text-color);
} */

.light-mode {
  --bg-color: #ffffff;
  --text-color: #000;
  --header-bg-color: #f0f0f0;
  --footer-bg-color: #f0f0f0;
  --card-bg-color: #f9f9f9;
  --button-bg-color: #7a4caf;
  --button-text-color: #fff;
  --button-hover-bg-color: #5a3f8c;
  --button-hover-text-color: #fff;
}

.dark-mode {
  --bg-color: #333;
  --text-color: #fff;
  --header-bg-color: #444;
  --footer-bg-color: #444;
  --card-bg-color: #525252;
  --button-bg-color: #7a4caf;
  --button-text-color: #fff;
  --button-hover-bg-color: #5a3f8c;
  --button-hover-text-color: #fff;
}
</style>
