<script setup>
const props = defineProps(["posts"]);
const defaultImg='/img/blog-default.jpeg'
</script>

<template>
  <div
    v-for="post in props.posts"
    :key="post.slug"
    class="bg-white rounded-lg shadow-md overflow-hidden hover:opacity-75 mt-4"
  >
    <NuxtLink :to="post._path">
      <img
        :src="
          post.cover
            ? `${post.cover}`
            : defaultImg
        "
        class="w-full h-48 object-cover"
        alt="image"
      />
    </NuxtLink>
    <div class="p-6">
      <h2 class="text-xl font-bold mb-2">{{ post.title }}</h2>
      <p class="text-gray-700 mb-4">{{ post.description }}</p>
      <NuxtLink
        :to="post._path"
        class="inline-block bg-blue-500 hover:bg-blue-700 text-white py-2 px-4 rounded float-right mb-8"
        >Read More
      </NuxtLink>
    </div>
  </div>
</template>
