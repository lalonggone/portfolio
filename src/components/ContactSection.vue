<template>
  <div class="contact-section">
    <h1>drop me a line</h1>
    <form action="https://formspree.io/f/meojqgbo" method="POST">
      <div class="form-group">
        <label for="name">name</label>
        <input type="text" name="name" id="name" v-model="form.name" required />
      </div>
      <div class="form-group">
        <label for="email">email</label>
        <input type="email" name="email" id="email" v-model="form.email" required />
      </div>
      <div class="form-group">
        <label for="message">message</label>
        <textarea name="message" id="message" v-model="form.message" required></textarea>
      </div>
      <button class="btn-submit" type="submit">send it</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'Contact',
  setup() {
    const form = ref({
      name: '',
      email: '',
      message: ''
    });

    return {
      form
    };
  }
});
</script>

<style lang="scss" scoped>
.contact-section {
  max-width: 600px;
  margin: 0 auto;
  padding: 50px;
  background-color: var(--bg-color);
  border-radius: 8px;

  h1 {
    margin: 40px 0 20px 0;
    font-size: 2em;
    color: var(--text-color);
  }

  .form-group {
    margin-bottom: 15px;

    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
      color: var(--text-color);
    }

    input,
    textarea {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
      background-color: var(--input-bg-color);
      color: var(--input-text-color);
    }

    textarea {
      height: 100px;
      resize: vertical;
    }
  }

  .btn-submit {
    display: inline-block;
    margin-top: 20px;
    padding: 10px 20px;
    background-color: var(--button-bg-color);
    color: var(--button-text-color);
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s;

    &:hover {
      background-color: var(--button-hover-bg-color);
    }
  }
}

// /* Light mode variables */
// .light-mode {
//   --bg-color: #ffffff;
//   --text-color: #000;
//   --input-bg-color: #ffffff;
//   --input-text-color: #000;
//   --button-bg-color: #7a4caf;
//   --button-text-color: #fff;
//   --button-hover-bg-color: #5a3f8c;
// }

// /* Dark mode variables */
// .dark-mode {
//   --bg-color: #333;
//   --text-color: #fff;
//   --input-bg-color: #444;
//   --input-text-color: #fff;
//   --button-bg-color: #7a4caf;
//   --button-text-color: #fff;
//   --button-hover-bg-color: #5a3f8c;
// }
</style>