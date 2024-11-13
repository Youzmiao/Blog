<template>
    <header class="header">
      <h1>{{ name }}</h1>
      <p>{{ title }}</p>
    </header>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const name = ref("你的姓名");
  const title = ref("前端开发工程师");
  </script>
  
  <style scoped>
  </style>
  