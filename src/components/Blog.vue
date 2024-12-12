<template>
    <section id="blog" class="py-20">
      <div class="max-w-6xl mx-auto px-4">
        <h2 class="text-4xl font-bold text-gray-800 mb-12 text-center">Latest Blog Posts</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <article v-for="post in 2" :key="post" class="bg-gray-50 rounded-lg overflow-hidden shadow-lg">
            <img src="../assets/cat.jpg" alt="Blog 1" class="w-full h-48 object-cover" />
            <div class="p-6">
              <h3 class="text-xl font-semibold text-gray-800 mb-2">
                Understanding Modern Web Development
              </h3>
              <p class="text-gray-600 mb-4">
                Exploring the latest trends and best practices in web development...
              </p>
              <div class="flex items-center justify-between">
                <span class="text-pink-500 hover:text-pink-600 transition-colors duration-300">Read More →</span>
                <span class="text-gray-500">5 min read</span>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>

  </script>
  
 
 
<style scoped>
 
</style>