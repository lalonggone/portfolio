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
@import '_variables.scss';

html {
  scroll-behavior: smooth;
}

#app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px 20px;
  font-family: Montserrat, sans-serif;
  color: var(--text-color);
  transition: color 1.5s;
}

button {
  cursor: pointer;
  pointer-events: auto;
}

body {
  background-color: var(--bg-color);
}
</style>
