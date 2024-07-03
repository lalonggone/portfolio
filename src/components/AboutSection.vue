<template>
    <section class="about-section">
      <div class="about-content">
        <h1 class="about-title">About Me</h1>
        <p class="about-description">
          Hello! I'm Laura, a passionate software developer with a love for creating innovative solutions. With a background in XYZ and experience in various technologies such as JavaScript, Vue.js, and more, I am always eager to take on new challenges and learn new skills.
        </p>
        <p class="about-description">
          When I'm not coding, I enjoy hiking, photography, and exploring the great outdoors. I believe in continuous learning and strive to improve my skills every day.
        </p>
      </div>
      <div class="about-image">
        <!-- <img src="../assets/your-photo.jpg" alt="Laura Long" class="profile-image" /> -->
      </div>
    </section>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'About'
  });
  </script>
  
  <style lang="scss" scoped>
  .about-section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 50px;
    background-color: var(--bg-color);
    // color: var(--text-color);
  
    .about-content {
      flex: 1;
      margin-right: 20px;
  
      .about-title {
        font-size: 2.5rem;
        margin: 40px;
      }
  
      .about-description {
        font-size: 1.1rem;
        line-height: 1.6;
        margin-bottom: 20px;
      }
    }
  
    .about-image {
      flex: 1;
      text-align: center;
  
      .profile-image {
        max-width: 100%;
        height: auto;
        border-radius: 10px;
        border: 2px solid #ccc;
      }
    }
  }
  </style>
  