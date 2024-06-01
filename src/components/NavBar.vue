<template>
  <header class="header">
    <div class="logo-container">
      <a @click="scrollToTop" class="scroll-to-top">
        <img src="../assets/LL Logo.jpg" alt="Logo" class="logo">
        <span class="header-name"> < LauraLong /> </span>
      </a>
    </div>
    <div class="nav-switch-container">
      <nav class="header-nav">
        <ul class="nav-list">
          <li class="nav-item"><a href="#projects" class="nav-link">projects</a></li>
          <li class="nav-item"><a href="#about" class="nav-link">about</a></li>
          <li class="nav-item"><a href="#contact" class="nav-link">contact</a></li>
        </ul>
      </nav>
      <v-switch
        v-model="localIsDarkMode"
        @change="emitToggleTheme"
        color="black"
        label="dark"
        hide-details
        inset
      ></v-switch>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from 'vue';

export default defineComponent({
  name: 'Header',
  props: {
    isDarkMode: {
      type: Boolean,
      required: true,
    }
  },
  setup(props, { emit }) {
    const localIsDarkMode = ref(props.isDarkMode);

    const emitToggleTheme = () => {
      emit('update:isDarkMode', localIsDarkMode.value);
    };

    function scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }

    watch(() => props.isDarkMode, (newVal) => {
      localIsDarkMode.value = newVal;
    });

    return { localIsDarkMode, scrollToTop, emitToggleTheme };
  }
});
</script>

<style lang="scss" scoped>
.header {
  position: sticky;
  top: 10px;
  background-color: var(--header-bg-color);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 0 0 20px;

  .logo-container {
    display: flex;
    align-items: center;

    .logo {
      width: 40px;
      height: auto;
      margin-right: 10px;
    }
    .scroll-to-top {
      text-decoration: none;
      display: flex;
      align-items: center;
      cursor: pointer;
    }

    .header-name {
      font-size: 26px;
    }
  }

  .nav-switch-container {
    display: flex;

    .v-switch {
      transform: scale(0.7);
    }
  }

  .header-nav {
    .nav-list {
      list-style: none;
      display: flex;
      justify-content: space-around;
      margin: 0;
      padding: 0;

      .nav-item {
        padding: 20px;

        .nav-link {
          text-decoration: none;
          color: var(--text-color);
          transition: color 0.5s;

          &:hover,
          &:focus {
            color: #aaa;
          }
        }
      }
    }
  }

  .theme-toggle {
    display: flex;
    align-items: center;

    #theme-switch {
      margin-right: 10px;
    }

    .theme-label {
      color: var(--text-color);
    }
  }
}
</style>

