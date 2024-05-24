<template>
    <section class="home-section">
      <div class="home-content">
        <h1 class="home-title">Howdy! I'm Laura.</h1>
        <p>I'm a passionate space cowgirl software developer specializing in .. blah blah blah... Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam nec purus et ante tincidunt aliquam. "You only yolo once".</p>
        <div class="skills-container">
          <h2>My Skills</h2>
          <ul class="skills-list">
            <li>JavaScript</li>
            <li>React.js</li>
            <li>PostgressQL</li>
            <li>Vue.js</li>
            <li>TypeScript</li>
            <li>HTML & CSS</li>
            <li>Node.js</li>
          </ul>
        </div>
        <a href="#projects" class="btn-see-my-work">See My Work</a>
      </div>
      <div class="home-image">
        <img src="../assets/FUTURE.jpg" alt="Purple ">
      </div>
    </section>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'HomeSection'
  });
  </script>
  
  <style lang="scss" scoped>
  .home-section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 50px;
  
    .home-content {
      flex: 1;
      margin-right: 20px;
  
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