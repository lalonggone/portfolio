<template>
  <section class="hero-section">
    <div class="hero-content">
      <h1 class="hero-title">Hi, I'm Laura.</h1>
      <p>I'm a freelance web developer </p>
      <div class="skills-container">
        <h2>My Skills</h2>
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" />
        <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg" />

        <Transition name="fade">
          <ul v-if="loaded" class="skills-list">
            <!-- <li v-for="(skill, index) in skills" :key="index">
              {{ skill }}
            </li> -->
          </ul>
        </Transition>
      </div>
      <a href="#projects" class="btn-see-my-work">See My Work</a>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HeroSection',
  data() {
    return {
      // skills: ['JavaScript', 'React.js', 'PostgreSQL', 'Vue.js', 'TypeScript', 'HTML & CSS', 'SCSS', 'Node.js'],
      loaded: false
    }
  },
  mounted() {
    this.loaded = true;
    // console.log('Skills loaded:', this.skills);
  }
});
</script>

<style lang="scss" scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: translateY(10px);
}

.hero-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 50px;

  .hero-content {
    flex: 1;

    .hero-title {
      font-size: 4.5rem;
      margin: 0;
    }

    .skills-container {
      margin-top: 20px;

      .skills-icon {
        width: 50px;
        height: 50px;
        margin: 10px;
      }

      .skills-list {
        display: flex;
        list-style-type: none;
        padding: 0;

        li {
          padding: 5px 0;
        }
      }
    }

    .btn-see-my-work {
      display: inline-block;
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #7a4caf;
      color: white;
      text-decoration: none;
      border-radius: 5px;
    }
  }

  .hero-image {
    flex: 1;

    img {
      width: 80%;
      border-radius: 10px;
      border: 2px solid #ccc;
    }
  }
}
</style>
