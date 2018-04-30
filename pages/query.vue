<template>
  <div>
    <p>Current data received from async data (should be equal to page number): {{ receivedData }}</p>
    <nuxt-link :to="`/query?page=${Number(receivedData)-1}`">Backward</nuxt-link>
    <nuxt-link :to="`/query?page=${Number(receivedData)+1}`">Forward</nuxt-link>
  </div>

</template>

<script>

export default {
  watchQuery: ['page'],
  key: to => to.fullPath,
  data () {
    return {
      receivedData: 0
    }
  },
  async asyncData ({ query }) {
    console.log('ASYNC ', query.page)
    await Promise.resolve(r => setTimeout(r, 500))
    return { receivedData: query.page || 1 }
  }
}

</script>
