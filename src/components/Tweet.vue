<template>
  <p>
    Will show {{ this.url }} ...
  </p>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Tweet',
  props: {
    url: {
      type: String,
      required: true
    }
  }
})
</script>
