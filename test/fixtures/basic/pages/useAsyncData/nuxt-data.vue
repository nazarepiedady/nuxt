<template>
  <div
    v-if="status === 'success'"
    v-text="'resolved:' + data.resolved"
  />
  <div
    v-else
    v-text="'loading'"
  />
</template>

<script setup>
useNuxtData('call')
const { data, status } = await useAsyncData('call', () => Promise.resolve({ resolved: true }), { server: false })
</script>
