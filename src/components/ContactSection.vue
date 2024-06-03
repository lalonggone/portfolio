<template>
  <div class="contact-section">
    <h1>drop me a line</h1>
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="name">name</label>
        <input type="text" id="name" v-model="form.name" required />
      </div>
      <div class="form-group">
        <label for="email">email</label>
        <input type="email" id="email" v-model="form.email" required />
      </div>
      <div class="form-group">
        <label for="message">message</label>
        <textarea id="message" v-model="form.message" required></textarea>
      </div>
      <button className="btn-submit" type="submit">send it</button>
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

    function submitForm() {
      console.log('Form submitted:', form.value);
      form.value = {
        name: '',
        email: '',
        message: ''
      };
    };

    return {
      form,
      submitForm
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
  }

  p {
    margin-bottom: 20px;
  }

  .form-group {
    margin-bottom: 15px;

    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }

    input,
    textarea {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
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
    background-color: #7a4caf;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s;

    &:hover {
      background-color: #45a049;
    }
  }
}
</style>
