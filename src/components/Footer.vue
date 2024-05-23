<template>
    <footer>
      <div class="footer-content">
        <a href="#home">Back to Top</a>
        <div class="social-links">
          <a href="https://github.com/lalonggone" target="_blank">GitHub</a>
          <a href="https://linkedin.com/in/lalonggone" target="_blank">LinkedIn</a>
          <!-- <a href="https://twitter.com/yourusername" target="_blank">Twitter</a> -->
        </div>
        <p>© {{ currentYear }} Laura Long. All rights reserved.</p>
      </div>
    </footer>
  </template>
  
  <script lang="ts">
  import { defineComponent, computed } from 'vue';
  
  export default defineComponent({
    name: 'Footer',
    setup() {
      const currentYear = computed(() => new Date().getFullYear());
      return { currentYear };
    }
  });
  </script>
  
  <style scoped>
  footer {
    background-color: #333;
    color: #fff;
    padding: 20px;
    text-align: center;
  }
  .footer-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }
  .social-links a {
    color: #fff;
    margin: 0 10px;
  }
  p {
  font-size: 0.8rem;
}
  </style>
  