<template>
    <div class="contact-section">
      <h1>Contact Me</h1>
      <p>Call me beep me if you wanna reach me! JK - just fill out the form below.</p>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" v-model="form.name" required />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="form.email" required />
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" v-model="form.message" required></textarea>
        </div>
        <button className="btn-submit" type="submit">Send Message</button>
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
  
      const submitForm = () => {
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
  
  <style scoped>
  .contact-section {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    background-color: var(--bg-color);
    color: var(--text-color);
    border-radius: 8px;
  }
  
  .contact-section h1 {
    margin-bottom: 20px;
    font-size: 2em;
  }
  
  .contact-section p {
    margin-bottom: 20px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  .form-group label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
  }
  
  .form-group input,
  .form-group textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  .form-group textarea {
    height: 100px;
    resize: vertical;
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
  }
  
  .btn-submit:hover {
    background-color: #45a049;
  }
  </style>
  