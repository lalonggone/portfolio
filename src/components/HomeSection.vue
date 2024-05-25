<template>
  <section class="home-section">
    <div class="home-content">
      <h1 class="home-title">Howdy! I'm Laura.</h1>
      <p>I'm a passionate space cowgirl software developer specializing in .. blah blah blah... Lorem ipsum dolor sit
        amet, consectetur adipiscing elit. Nullam nec purus et ante tincidunt aliquam. "You only yolo once".</p>
      <div class="skills-container">
        <h2>My Skills</h2>
        <TransitionGroup v-if="loaded" name="fade" tag="ul" class="skills-list">
          <li v-for="(skill, index) in skills" :key="index">
            {{ skill }}
          </li>
        </TransitionGroup>
      </div>
      <a href="#projects" class="btn-see-my-work">See My Work</a>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeSection',
  data() {
    return {
      skills: ['JavaScript', 'React.js', 'PostgreSQL', 'Vue.js', 'TypeScript', 'HTML & CSS', 'SCSS', 'Node.js'],
      loaded: false
    }
  },
  mounted() {
    this.loaded = true;
    console.log('Skills loaded:', this.skills);
  }
});
</script>

<style lang="scss" scoped>
.fade-enter-active, .fade-leave-active {
  transition: all 0.5s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.home-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 50px;

  .home-content {
    flex: 1;

    .home-title {
      font-size: 2.5rem;
      margin: 0;
    }

    .skills-container {
      margin-top: 20px;

      .skills-list {
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

  .home-image {
    flex: 1;

    img {
      width: 80%;
      border-radius: 10px;
      border: 2px solid #ccc;
    }
  }
}
</style>
