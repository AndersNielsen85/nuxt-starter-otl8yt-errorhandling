<template>
  <div>
    {{ data }}
  </div>
</template>
<script lang="ts">

export default defineComponent({
  async setup() {
    await Promise.resolve(true);
const route = useRoute();
const { data, refresh } = await useFetch('https://httpstat.us/404');

if (!data.value) {
  console.log('throw error')
  throw createError({ statusCode: 404, statusMessage: 'Something went wrong' })
}
  },
});
</script>
