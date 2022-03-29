### vue3-state-management

vue3 state management solutions.


### create： /store/useUserStore.js

```javascript
import { reactive, readonly } from 'vue'
// import { apiLogin } from '@/api/user' // logins api's demo,you can use your own api.
const initState = reactive({
  name: 'co2color',
  isLogin: false,
})

const state = readonly(initState) //--Avoid directly changing the state value.

export const actions = {
  async useLogin(name: string, password: string) {
    // const res = await apiLogin(name, password)
    const res = { loginStatus: true }
    initState.isLogin = res.loginStatus
    initState.name = name
  },
}
export const useUserStore = () => ({
  state,
  actions,
})

```

### use:

```javascript
<script setup lang='ts'>
import { useUserStore } from '@/store'
const store = useUserStore()
console.log(store.state)
setTimeout(() => {
  store.actions.useLogin('handsome co2color', '123456')
}, 1000)
console.log(store.state)
</script>

<template>
  <h1>{{ store.state }}</h1>
</template>
```
