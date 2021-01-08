<template>
  <div
    class="rounded bg-grey-400 w-2 h-2"
    :style="{
      top: `${y}px`,
      left: `${x}px`,
    }"
  />
</template>

<script>
import { ref } from '@nuxtjs/composition-api'

export default {
  name: 'Agent',

  setup() {
    const x = ref(0)
    const y = ref(0)

    return {
      x,
      y,
    }
  },
}
</script>
