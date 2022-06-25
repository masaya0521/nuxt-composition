<template>
  <div>
    <h1>{{ text }}</h1>
    {{ computed1 }} <br/>
    {{ computed2 }} <br/>
    {{ method("です") }}
  </div>
</template>

<script lang="ts">
import { computed, defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const text = 'Hello, World!'

    const computed1 = computed(() => text + "test")
    const computed2 = computed(() => text + "2")

    const method = (a: string) => {
      return "method test" + a
    }

    return {
      text,
      computed1,
      computed2,
      method,
    }
  },
})
</script>