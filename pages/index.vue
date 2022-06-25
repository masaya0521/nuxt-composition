<template>
  <div>
    <h1>{{ text }}</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const text = 'Hello, World!'

    return {
      text,
    }
  },
})
</script>