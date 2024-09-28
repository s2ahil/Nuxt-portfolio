<script setup>
const query = gql`
  {
    viewer {
      pinnedItems(first: 6) {
        totalCount
        nodes {
          ... on Repository {
            id
            name
            createdAt
            description
            url
            forks {
              totalCount
            }
            watchers {
              totalCount
            }
            stargazers {
              totalCount
            }
          }
        }
      }
    }
  }
`;

const { data, error } = await useAsyncQuery(query);
</script>
<template>
  <h1 class="text-3xl my-8">Pinned Projects</h1>
  <p class="text-lg mb-8">Here are some of my pinned projects on GitHub.</p>
  <section class="grid md:grid-cols-2 gap-10">
    <div
      v-for="project in data?.viewer.pinnedItems.nodes"
      :key="project.id"
      class="p-8 border-4 my-4 rounded-lg hover:bg-gray-50"
    >
      <a :href="project.url" target="_blank">
        <h2 class="text-2xl text-indigo-800 font-semibold mb-2 hover:underline">
          {{ project.name }}
        </h2>
      </a>
      <p>{{ project.description }}</p>
      <div class="mt-4 flex items-center gap-2">
        <Icon name="fontisto:star" size="1.1rem" class="text-indigo-700" />
        <div>Stars: {{ project.stargazers.totalCount }}</div>
        <Icon
          name="system-uicons:branch"
          size="1.1rem"
          class="text-indigo-800"
        />
        <div>Forks: {{ project.forks.totalCount }}</div>
        <Icon name="system-uicons:eye" size="1.1rem" class="text-indigo-700" />
        <div>Watchers: {{ project.watchers.totalCount }}</div>
      </div>
    </div>
  </section>
</template>
