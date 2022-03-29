<script setup lang="ts">
import { ref } from 'vue'
import { useUserStore } from '../store'
const store = useUserStore()
const showRedSpan = ref(false)
const loginClick = () => {
  store.actions.useLogin('handsome co2color', '123456')
  showRedSpan.value = true
}
</script>
<template>
  <div>
    <span>son1 - - -{{ store.state }}</span>
    <button style="margin: 0 10px;" @click="loginClick">click son1 to login</button>
    <span style="color: red;" v-if="showRedSpan">Now the status of both son1 and son2 has changed.</span>
  </div>
</template>
