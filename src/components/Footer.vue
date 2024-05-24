<template>
  <footer class="footer">
    <div class="footer-content">
      <a href="#home" class="footer-link">Back to Top</a>
      <div class="social-links">
        <a href="https://github.com/lalonggone" target="_blank" class="social-link">GitHub</a>
        <a href="https://linkedin.com/in/lalonggone" target="_blank" class="social-link">LinkedIn</a>
      </div>
      <p class="footer-text">© {{ currentYear }} Laura Long. All rights reserved.</p>
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

<style lang="scss" scoped>
.footer {
  background-color: var(--footer-bg-color);
  color: var(--footer-text-color);
  padding: 20px;
  text-align: center;

  .footer-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;

    .footer-link {
      color: var(--footer-text-color);
      text-decoration: none;
    }

    .social-links {
      display: flex;
      justify-content: center;
      gap: 10px;

      .social-link {
        color: var(--footer-text-color);
        margin: 0 10px;
        text-decoration: none;
      }
    }

    .footer-text {
      font-size: 0.8rem;
    }
  }
}
</style>
