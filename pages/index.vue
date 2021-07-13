<template>
  <div>
    <div v-if="!$fetchState.pending">fetched data!</div>
    <div v-else>fetching still....</div>
  </div>
</template>

<script>
export default {
  async asyncData({ isDev }) {
    console.log('is dev ?', isDev)
    const call = await fetch('https://jsonplaceholder.typicode.com/todos/1')
    const res = await call.json()
    console.log('res', res)
  }
}
</script>
