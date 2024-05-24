<template>
  <header class="header">
    <div class="logo-container">
      <img src="../assets/LL Logo.jpg" alt="Logo" class="logo">
      <span class="header-name">Laura Long</span>
    </div>
    <nav class="header-nav">
      <ul class="nav-list">
        <!-- <li class="nav-item"><a href="#home" class="nav-link">home</a></li> -->
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

    watch(() => props.isDarkMode, (newVal) => {
      localIsDarkMode.value = newVal;
    });

    return { localIsDarkMode, emitToggleTheme };
  }
});
</script>

<style lang="scss" scoped>
.header {
  position: sticky;
  top: 0;
  background-color: var(--header-bg-color);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;

  .logo-container {
    display: flex;
    align-items: center;

    .logo {
      width: 40px;
      height: auto;
      margin-right: 10px;
    }

    .header-name {
      color: var(--text-color);
      font-size: 26px;
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
          transition: color 0.3s;

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

