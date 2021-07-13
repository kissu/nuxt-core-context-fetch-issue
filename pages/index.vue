<template>
  <div>
    <template v-if="isFetchingStillPending">fetched data!</template>
    <div v-else>fetching still....</div>
  </div>
</template>

<script>
export default {
  async fetch({ isDev }) {
    console.log('is dev', isDev)
    const call = await fetch('https://jsonplaceholder.typicode.com/todos/1')
    const res = await call.json()
    console.log('res', res)
  },
  computed: {
    isFetchingStillPending() {
      return !this.$fetchState?.pending
    }
  },
}
</script>
