<template>
    <div>
      <button @click="toggle">Toggle Items</button>
      <transition-group name="fade" tag="ul">
        <li v-for="item in items" :key="item" class="item">{{ item }}</li>
      </transition-group>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  
  export default defineComponent({
    name: 'SimpleExample',
    setup() {
      const items = ref([1, 2, 3, 4, 5]);
      const toggle = () => {
        if (items.value.length) {
          items.value = [];
        } else {
          items.value = [1, 2, 3, 4, 5];
        }
      };
      return { items, toggle };
    }
  });
  </script>
  
  <style scoped>
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter-from, .fade-leave-to {
    opacity: 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  .item {
    padding: 10px;
    margin: 5px 0;
    background: #eee;
    border: 1px solid #ddd;
  }
  </style>
  