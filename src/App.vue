<template>
  <div id="app">
    <Header @toggle-theme="toggleTheme" />
    <main id="content">
      <section id="home">
        <HomeSection />
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
    </main>
    <Footer />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed, watch } from 'vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import HomeSection from './components/HomeSection.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import AboutSection from './components/AboutSection.vue';
import ContactSection from './components/ContactSection.vue';

export default defineComponent({
  name: 'App',
  components: {
    Header,
    Footer,
    HomeSection,
    ProjectsSection,
    AboutSection,
    ContactSection
  },
  setup() {
    const isDarkMode = ref(false);

    const toggleTheme = (isDark: boolean) => {
      isDarkMode.value = isDark;
    };

    const themeClass = computed(() => (isDarkMode.value ? 'dark-mode' : 'light-mode'));

    watch(themeClass, (newClass, oldClass) => {
      document.body.classList.remove(oldClass);
      document.body.classList.add(newClass);
    });

    return { toggleTheme, themeClass };
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
  padding: 20px;
}

.light-mode {
  --bg-color: #ffffff;
  --text-color: #000;
  --header-bg-color: #f0f0f0;
  --footer-bg-color: #f0f0f0;
  background-color: var(--bg-color);
  color: var(--text-color);
}

.dark-mode {
  --bg-color: #333;
  --text-color: #fff;
  --header-bg-color: #444;
  --footer-bg-color: #444;
  background-color: var(--bg-color);
  color: var(--text-color);
}

header, footer {
  background-color: var(--header-bg-color);
  color: var(--text-color);
}


body.light-mode {
  background-color: var(--bg-color);
  color: var(--text-color);
}

body.dark-mode {
  background-color: var(--bg-color);
  color: var(--text-color);
}
</style>
