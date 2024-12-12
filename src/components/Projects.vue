<template>
  <section id="projects" class="py-20">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-4xl font-bold  mb-8 text-center">Featured Projects</h2>
      <span class=" bg-black h-1 w-10 block mx-auto mb-32"></span>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="project in projects" 
          :key="project.id" 
          class="group relative"
        >
          <!-- Main Card Container with skewed edges -->
          <div class="relative bg-[#e1d8ee] p-6 transform -skew-x-2">
            <!-- Profile Section -->
            <div class="flex items-start mb-4">
              <div class="relative w-24 h-24 mr-4 transform skew-x-2">
                <img 
                  :src="project.image" 
                  :alt="project.title"
                  class="w-full h-full object-cover rounded-lg border-4 border-gray-900"
                />
              </div>
              <div class="transform skew-x-2">
                <h3 class="text-2xl font-bold text-gray-900 mb-2">{{ project.title }}</h3>
                <div class="bg-gray-800 text-white px-3 py-1 rounded-full text-sm inline-block">
                  {{ project.role }}
                </div>
              </div>
            </div>
            
            <!-- Description -->
            <p class="text-gray-800 mb-4 transform skew-x-2">
              {{ project.description }}
            </p>

            <!-- Tech Stack -->
            <div class="transform skew-x-2">
              <div class="flex flex-wrap gap-2">
                <span 
                  v-for="tech in project.technologies" 
                  :key="tech"
                  class="bg-gray-800 text-white px-3 py-1 rounded-full text-sm"
                >
                  @{{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    id: 1,
    title: "Project One",
    role: "LEAD DEVELOPER",
    image: "../assets/project1.jpg",
    description: "A full-stack application built with Vue.js and Node.js, featuring real-time data synchronization.",
    technologies: ["vue", "nodejs", "tailwind"]
  },
  {
    id: 2,
    title: "Project Two",
    role: "FRONTEND DEVELOPER",
    image: "../assets/project2.jpg",
    description: "An interactive dashboard with advanced data visualization capabilities.",
    technologies: ["react", "d3", "typescript"]
  },
  {
    id: 3,
    title: "Project Three",
    role: "UI/UX DESIGNER",
    image: "../assets/project3.jpg",
    description: "A modern e-commerce platform with seamless user experience and animations.",
    technologies: ["vue", "gsap", "firebase"]
  }
]
</script>

<style scoped>

</style>