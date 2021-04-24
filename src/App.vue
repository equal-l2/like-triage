<template>
  <main class="section container">
  <div class="columns">
    <div class="column is-1">
      <button class="button is-rounded" :disabled="!hasPrev" @click="dec">←</button>
    </div>
    <p class="column">
      <Tweet :url="url"></Tweet>
    </p>
    <div class="column is-1">
      <button class="button is-rounded" :disabled="!hasNext" @click="inc">→</button>
    </div>
  </div>
  <div class="buttons is-centered">
    <button class="button is-info is-bold"><b>Stay</b></button>
    <button class="button is-danger is-bold"><b>Remove</b></button>
  </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Tweet from './components/Tweet.vue'

export default defineComponent({
  name: 'App',
  components: {
    Tweet
  },
  data () {
    return {
      urls: [
        'https://twitter.com/EqualL2/status/1383877798863859718',
        'https://twitter.com/EqualL2/status/1385886417356611586',
        'https://twitter.com/EqualL2/status/1385830164571955201'
      ],
      index: 0
    }
  },
  computed: {
    url () {
      return this.urls[this.index]
    },
    hasNext () {
      return this.index < (this.urls.length - 1)
    },
    hasPrev () {
      return this.index > 0
    }
  },
  methods: {
    inc () {
      if (this.hasNext) this.index++
    },
    dec () {
      if (this.hasPrev) this.index--
    }
  }
})
</script>

<style lang="sass">
@import 'bulma/css/bulma.css'
</style>
