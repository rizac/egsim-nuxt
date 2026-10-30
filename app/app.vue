<template>
  <!--
  <div>
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
  </div>
  -->
  <div class="p-3">
    <h1>Models (raw response)</h1>
    <p v-if="pending">Loading...</p>
    <p v-else-if="error">Error {{ error.statusCode }}: {{ error.data }}</p>
    <pre v-else>{{ preview }}</pre>
  </div>
</template>

<script setup>
const { data, pending, error } = await useFetch('/api/query/models?name=Bindi')
const preview = computed(() => JSON.stringify(data.value, null, 2))
</script>
