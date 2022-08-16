<template>
  <div>
    This will be shown on errors<br>
     Code: {{ error.statusCode }}<br>
     Message: {{ error.statusMessage }}
  </div>
  <button @click="handleError">Clear error</button>
</template>

<script setup>
const props = defineProps({
  error: Object,
});

const handleError = () => clearError({ redirect: '/' });
</script>
