<template>
  <section class="hero-section">
    <div class="hero-content">
      <h1 class="hero-title">Hi, I'm Laura.</h1>
      <p class="hero-description">I'm a freelance web developer</p>
      <a href="#projects" class="btn-see-my-work">See My Work</a>
      <div class="skills-container">
        <!-- <h2>My Skills</h2> -->
        <div class="skills-icons">
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" alt="JavaScript" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" alt="React" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" alt="Vue" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" alt="TypeScript" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" alt="HTML5" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg" alt="Sass" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" alt="CSS3" />
          <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg" alt="Node.js" />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HeroSection',
});
</script>

<style lang="scss" scoped>
@import '../_variables.scss';

.hero-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 50px;

  @media (min-width: $screen-sm) {
    flex-direction: row;
    justify-content: space-between;
    padding: 10px;
  }

  .hero-content {
    flex: 1;

    .hero-title {
      font-size: 2.5rem;
      margin-top: 10vh;

      @media (min-width: $screen-md) {
        font-size: 4.5rem;
      }
    }

    .hero-description {
      font-size: 1.5rem;
      margin-top: 20px;

      @media (min-width: $screen-md) {
        font-size: 2rem;
      }
    }

    .skills-container {
      margin: 5vh;

      @media (min-width: $screen-sm) {
            margin: 10vh;
          }

          @media (min-width: $screen-md) {
            margin: 20vh;
          }

      .skills-icons {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

        .skills-icon {
          width: 40px;
          height: 40px;
          margin: 15px;
          transition: transform 0.2s;

          @media (min-width: $screen-sm) {
            width: 60px;
            height: 60px;
          }

          @media (min-width: $screen-md) {
            width: 80px;
            height: 80px;
          }

          &:hover {
            transform: scale(1.2);
          }
        }
      }
    }

    .btn-see-my-work {
      display: inline-block;
      margin-top: 20px;
      padding: 10px 20px;
      background-color: var(--button-bg-color);
      color: white;
      text-decoration: none;
      border-radius: 5px;
      transition: background-color 0.3s;

      &:hover {
        background-color: var(--button-hover-bg-color);
        font-weight: bold;
      }
    }
  }

  // .hero-image {
  //   flex: 1;

  //   img {
  //     width: 100%;
  //     border-radius: 10px;
  //     border: 2px solid #ccc;
  //   }
  // }
}
</style>