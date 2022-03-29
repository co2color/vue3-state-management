<script setup lang="ts">
import { useUserStore } from '../store'
const store = useUserStore()
</script>
<template>
  <span>son2 - - -{{ store.state }}</span>
</template>
