<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">vetur-apollo-intellisense</h1>
      <button @click="increment">Click to increment</button>
      <p>{{ count }}</p>
    </div>
  </div>
</template>

<script>
import gql from 'graphql-tag'
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo,
  },
  data() {
    return {
      count: 0,
    }
  },
  methods: {
    increment() {
      this.count++
    },
  },
  apollo: {
    user: {
      query: gql`
        query {
          hello
        }
      `,
    },
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
