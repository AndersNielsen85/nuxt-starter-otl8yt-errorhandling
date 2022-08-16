<template>
  <div>
    {{ data }}
  </div>
</template>
<script setup lang="ts">
const route = useRoute();
const { data, refresh } = await useFetch('https://httpstat.us/404');

if (!data.value) {
  throw createError({ statusCode: 404, statusMessage: 'Something went wrong' })
}
</script>
