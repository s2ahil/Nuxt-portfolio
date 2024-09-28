<script setup>
const { data: posts } = await useAsyncData('latest-posts', () => 
  queryContent('/blog').sort({ data: 1 }).limit(3).find()
);


</script>

<template>
  <section>
    <h1 class="text-5xl font-bold mt-20">Hello Folks, Im Sahil Pradhan</h1>
    <p class="text-base text-gray-900 p-2 italic">Mern Developer + Next js</p>
  </section>

  <section class="flex flex-col md:flex-row">
    <div class="md:w-3/4">
      <h2 class="text-3xl font-bold mt-8">My Story</h2>
      <p class="text-lg py-2">
        I am a full stack web developer from india , have experience in react ,
        express , next js . Additionally i also have some interest in android
        development (Flutter) .
      </p>
      <p class="text-lg py-2">
        Actively participate in hackathon , Got 4x hackathon wins
      </p>

      <p class="text-lg py-2">
        Worked in a college based startup (unistyl) contributed there by
        building ecommerce website for there clothing brand , contributing to
        increased sales and improved customer engagement.
      </p>
    </div>
    <img
      src="/assets/images/profile.jpg"
      class="w-[20rem] h-[20rem] md:max-w-sm mx-auto p-8 rounded-full object-cover"
      alt=""
    />
  </section>

  <section>
    <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
    <div class="grid md:grid-cols-3 pt-8 gap-10">
      <Post  :posts="posts" />
    </div>
  </section>
</template>

<!-- About Me
- Skills
- Projects
- Contact Info -->
