<template>
    <section class="projects-section">
      <!-- <h1 class="projects-title">projects</h1> -->
      <div class="projects-grid">
        <div class="project-card" v-for="project in projects" :key="project.id">
          <h2 class="project-title">{{ project.title }}</h2>
          <p class="project-description">{{ project.description }}</p>
          <a v-if="project.liveLink" :href="project.liveLink" target="_blank" class="project-link" title="View Live Project">link</a>
          <a v-if="project.sourceCode" :href="project.sourceCode" target="_blank" class="project-link" title="View Source Code">source</a>
        </div>
      </div>
    </section>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'ProjectsSection',
    setup() {
      const projects = ref([
        {
          id: 1,
          title: 'Kane Creek Comments',
          description: 'A full-stack web app that allows users to filter, search, and display thousands of survey responses regarding a development in Utah.',
          liveLink: 'https://kane-creek-comments.vercel.app/',
          sourceCode: 'https://github.com/lalonggone/kane-creek-comments-fe'
        },
        {
          id: 2,
          title: 'Travel Tracker',
          description: 'An app that allows users to login and manage trips. The user can view upcoming and pending trips, estimate costs, and book new trips. Written in vanilla Javascript!',
          liveLink: '',
          sourceCode: 'https://github.com/lalonggone/travel-tracker'
        },
        {
          id: 3,
          title: 'Moab Bike Hub',
          description: 'Coming soon - stay tuned!',
          liveLink: '',
          sourceCode: 'https://github.com/lalonggone/moab-bike-hub'
        },
        {
          id: 4,
          title: 'Rock Paper Scissors',
          description: 'A game featuring two modes - classic and EXTREME! Set up to be played against a computer that generates random choices against the user.',
          liveLink: 'https://rock-paper-scissors.vercel.app/',
          sourceCode: 'https://github.com/lalonggone/rockPaperScissors'
        },
        {
          id: 5,
          title: 'Kane Creek Survey',
          description: 'A handrolled form written in vanilla JS serving as a mock petition against the proposed development in the Colorado River corridor near Moab, Utah.',
          liveLink: 'https://lalonggone.github.io/kc-comp/index.html',
          sourceCode: 'https://github.com/lalonggone/kcpd-petition'
        },
        {
          id: 6,
          title: 'Blank',
          description: 'Coming soon - stay tuned!',
          liveLink: '',
          sourceCode: ''
        }
      ]);
  
      return { projects };
    }
  });
  </script>
  
  <style lang="scss" scoped>
  .projects-section {
    padding: 120px 50px;
    background-color: var(--bg-color);
    color: var(--text-color);
  
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 35px;
  
      .project-card {
        background-color: var(--card-bg-color);
        color: var(--text-color);
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        text-align: center;
        transition: background-color 0.3s, color 0.3s;
  
        .project-title {
          font-size: 1.5rem;
          margin-bottom: 10px;
        }
  
        .project-description {
          font-size: 1rem;
          margin-bottom: 20px;
        }
  
        .project-link {
          display: inline-block;
          margin: 0 10px;
          padding: 10px 20px;
          background-color: var(--button-bg-color);
          color: var(--button-text-color);
          text-decoration: none;
          border-radius: 5px;
          transition: background-color 0.3s, color 0.3s;
  
          &:hover {
            background-color: var(--button-hover-bg-color);
            color: var(--button-hover-text-color);
          }
        }
      }
    }
  }
  </style>