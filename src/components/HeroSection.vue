<template>
  <section class="hero-section">
    <div class="hero-content">
      <h1 class="hero-title">Hi, I'm Laura.</h1>
      <p class="hero-description">I'm a freelance web developer.</p>
      <a href="#projects" class="btn-my-work">See my work</a>
      <a href="#projects" class="btn-my-resume">Take a resume</a>
      <div class="skills-container">
        <div class="skills-icons">
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" alt="JavaScript" />
            <span class="skill-label">JavaScript</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" alt="React" />
            <span class="skill-label">React</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" alt="Vue" />
            <span class="skill-label">Vue</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" />
            <span class="skill-label">PostgreSQL</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" alt="TypeScript" />
            <span class="skill-label">TypeScript</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" alt="HTML5" />
            <span class="skill-label">HTML5</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg" alt="Sass" />
            <span class="skill-label">Sass</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" alt="CSS3" />
            <span class="skill-label">CSS3</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg" alt="Node.js" />
            <span class="skill-label">Node.js</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" alt="Git" />
            <span class="skill-label">Git</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vitejs/vitejs-original.svg" alt="ViteJS" />
            <span class="skill-label">ViteJS</span>
          </div>
          <div class="skill-wrapper">
            <img class="skills-icon" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/webpack/webpack-original.svg" alt="Webpack" />
            <span class="skill-label">Webpack</span>
          </div>
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
  margin-bottom: 20vh;
  
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
      margin: 20px;
      
      @media (min-width: $screen-md) {
        font-size: 2rem;
      }
    }
    
    .btn-my-work,
    .btn-my-resume {
      display: inline-block;
      font-weight: 500;
      margin: 20px;
      padding: 10px;
      background-color: var(--button-bg-color);
      color: white;
      text-decoration: none;
      border-radius: 5px;
      transition: background-color 0.3s;
      
      
      @media (min-width: $screen-sm) {
        width: 140px;
      }
      
      &:hover {
        background-color: var(--button-hover-bg-color);
      }
    }

    .skills-container {
      margin: 5vh;

      @media (min-width: $screen-sm) {
        margin: 10vh;
      }

      @media (min-width: $screen-md) {
        margin: 10vh 0 10vh 0;
      }

      .skills-icons {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

        .skill-wrapper {
          position: relative;
          margin: 15px;
          text-align: center;

          .skills-icon {
            width: 40px;
            height: 40px;
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
              transform: scale(1.1);
            }
          }

          .skill-label {
            position: absolute;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--text-color);
            padding: 2px 5px;
            border-radius: 3px;
            font-size: 0.9rem;
            opacity: 0;
            transition: opacity 0.2s;
            pointer-events: none;
            z-index: 1;
          }

          &:hover .skill-label {
            opacity: 1;
          }
        }
      }
    }

  }
}
</style>