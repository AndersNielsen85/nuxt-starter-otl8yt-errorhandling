<template>
  <div>
    Catch all route
    <div>
      <NuxtLink to="/">front</NuxtLink><br />
      <NuxtLink to="/1">first</NuxtLink><br />
      <NuxtLink to="/2">second</NuxtLink><br />
      <button @click="refresh">Force refresh data</button>
    </div>
    Data based on route {{ route.fullPath }}
    {{ data }}
  </div>
</template>
<script setup lang="ts">
const route = useRoute();
const { data, refresh } = await useFetch(
  'https://jsonplaceholder.typicode.com/posts/' + route.fullPath
);

//onMounted(() => {
//  refresh();
//});
</script>
