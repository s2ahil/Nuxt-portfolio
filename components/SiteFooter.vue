<script>
export default {
  data() {
    return {
      links: [
        {
          name: "GitHub",
          href: "https://github.com/s2ahil",
          icon: "entypo-social:github-with-circle",
        },
        {
          name: "Twitter",
          href: "https://twitter.com/s2ahil",
          icon: "entypo-social:twitter",
        },
       
        {
          name: "LinkedIn",
          href: "https://www.linkedin.com/in/sahil-pradhan-46a0a31b7/",
          icon: "entypo-social:linkedin-with-circle",
        },
   
      ],
    };
  },
};
</script>

<template>
  <footer class="bg-gray-800 p-4 mt-4">
    <section
      class="mx-auto max-w-7xl px-2 sm:px-4 lg:py-6 text-gray-300 flex flex-row"
    >
      <p class="flex-1">Sahil Pradhan 2024 . All Rights Reserved</p>
      <div class="flex flex-row justify-center gap-4 mb-4 mt-2">
        <a v-for="link in links" :key="link.name" :href="link.href">
          <Icon :name="link.icon" size="1.5rem" class="text-gray-300"></Icon>
        </a>
      </div>
    </section>
  </footer>
</template>
