<template>
    <div class="max-w-4xl mx-auto px-4 py-12 sm:px-6 lg:px-8">
      <h1 class="text-4xl font-extrabold text-gray-900 mb-8 animate-fade-in-down">
        My Tech Stack & Socials
      </h1>
  
      <!-- Socials Section -->
      <section class="mb-12">
        <h2 class="text-2xl font-bold text-gray-800 mb-4">Connect With Me at <a href="mailto:sahilpradhan411@gmail.com" class="underline text-blue-500">Email</a></h2>
        <div class="flex space-x-4">
          <a
            v-for="social in socials"
            :key="social.name"
            :href="social.url"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 hover:text-gray-900 transition-colors duration-300"
          >
            <component :is="social.icon" class="h-8 w-8" />
            <span class="sr-only">{{ social.name }}</span>
          </a>
        </div>
      </section>
  
      <!-- Tech Stack Section -->
      <section class="mb-12  ">
        <h2 class="text-2xl font-bold text-gray-800 mb-4">My Tech Stack</h2>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
          <div
            v-for="tech in techStack"
            :key="tech.name"
            class="bg-white p-4 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300  hover:bg-blue-200"
          >
            <NuxtIcon :name="tech.icon" class="h-12 w-12 mx-auto mb-2" />
            <h3 class="text-center font-semibold text-gray-700">{{ tech.name }}</h3>
          </div>
        </div>
      </section>
  
    
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import {
    Github,
    Twitter,
    LinkedinIcon,
    Mail
  
  } from 'lucide-vue-next';
  
  // Social Links with icons from lucide-vue-next
  const socials = ref([
    { name: 'GitHub', url: 'https://github.com/s2ahil', icon: Github },
    { name: 'Twitter/X', url: 'https://x.com/s2ahil', icon: Twitter },
    { name: 'LinkedIn', url: 'https://www.linkedin.com/in/sahil-pradhan-46a0a31b7/', icon: LinkedinIcon },
    
  ]);
  
  // Tech Stack with Nuxt Icons
  const techStack = ref([
    { name: 'React', icon: 'logos-react' },
    { name: 'Node.js', icon: 'logos-nodejs' },
    { name: 'Express', icon: 'logos-express' },
    { name: 'MongoDB', icon: 'logos-mongodb' },
    { name: 'Next.js', icon: 'logos-nextjs' },
    { name: 'Nuxt.js', icon: 'logos-nuxtjs' },
    { name: 'Tailwind CSS', icon: 'logos-tailwindcss-icon' }
  ]);
 
  </script>
  
  <style scoped>
  @keyframes fadeInDown {
    from {
      opacity: 0;
      transform: translateY(-20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .animate-fade-in-down {
    animation: fadeInDown 0.5s ease-out;
  }
  </style>
  