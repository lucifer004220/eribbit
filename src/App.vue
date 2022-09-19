<template>
  <div>
    <!-- state -->
    <p>{{ $store.state.username }}</p>
    <!-- getters -->
    <p>{{ $store.getters.newName }}</p>
    <button @click="fn">改名</button>
  </div>
</template>

<script>
import { useStore } from 'vuex'
export default {
  name: 'App',
  setup () {
    const store = useStore()
    console.log(store.state.username)
    console.log(store.getters.newName);
    const fn = () => {
      store.commit('updateName')
    }
    return { fn }
  }
}
</script>

<style>
</style>
