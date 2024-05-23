<template>
  <header class="header">
    <div class="logo-container">
      <img src="../assets/LL Logo.jpg" alt="Logo" class="logo">
      <span class="header-name">Laura Long</span>
    </div>
    <nav class="header-nav">
      <ul class="nav-list">
        <li class="nav-item"><a href="#home" class="nav-link">Home</a></li>
        <li class="nav-item"><a href="#projects" class="nav-link">Projects</a></li>
        <li class="nav-item"><a href="#about" class="nav-link">About Me</a></li>
        <li class="nav-item"><a href="#contact" class="nav-link">Contact</a></li>
      </ul>
    </nav>
    <div class="theme-toggle">
      <input type="checkbox" id="theme-switch" @change="toggleTheme" />
      <label for="theme-switch" class="theme-label">Toggle Theme</label>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Header',
  methods: {
    toggleTheme(event: Event) {
      const checked = (event.target as HTMLInputElement).checked;
      this.$emit('toggle-theme', checked);
    }
  }
});
</script>

<style scoped>
.header {
  position: sticky;
  top: 0;
  background-color: var(--header-bg-color);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  width: 40px;
  height: auto;
  margin-right: 10px;
}

.header-name {
  color: var(--text-color);
  font-size: 20px;
  font-family: 'Arial', sans-serif;
}

.header-nav .nav-list {
  list-style: none;
  display: flex;
  justify-content: space-around;
  margin: 0;
  padding: 0;
}

.nav-item {
  padding: 20px;
}

.nav-link {
  text-decoration: none;
  color: var(--text-color);
  transition: color 0.3s;
}

.nav-link:hover, .nav-link:focus {
  color: #aaa;
}

.theme-toggle {
  display: flex;
  align-items: center;
}

#theme-switch {
  margin-right: 10px;
}

.theme-label {
  color: var(--text-color);
}
</style>
