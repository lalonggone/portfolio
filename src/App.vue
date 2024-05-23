<template>
  <div id="app">
    <Header />
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
    <Footer />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
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
  }
});
</script>

<style>
section {
  min-height: 100vh
}
html {
  scroll-behavior: smooth;
}
</style>
