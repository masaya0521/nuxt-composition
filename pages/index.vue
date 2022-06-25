<template>
  <div>
    <h1>{{ text }}</h1>
    {{ textRef }} <br/>
    {{ dataReactive }} <br/>
    {{ computed1 }} <br/>
    {{ computed2 }} <br/>
    {{ method("です") }}
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref, reactive } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const text: string = 'Hello, World!'

    // data
    const textRef = ref("ref data") 
    // data こっちの方がv2のdataに近い？
    const dataReactive = reactive({
      form: {
        name: '',
      },
      users: [],
    })

    // computed
    const computed1 = computed(() => text + "computed1") 
    const computed2 = computed(() => text + "computed2")

    // method
    const method = (a: string) => {
      return "method" + a
    }   

    // createdわからん
    setTimeout(() => {
      console.log("created")
    }, 3000);

    return {
      text,
      textRef,
      dataReactive,
      computed1,
      computed2,
      method,
    }
  },
})
</script>