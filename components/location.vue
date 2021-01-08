<template>
  <div
    class="w-2 h-2 bg-black absolute"
    :class="{
      'bg-green-400': type === 'source',
      'bg-red-400': type === 'destination',
      'bg-yellow-400': type === 'busy-destination',
    }"
    :style="{
      top: `${y}px`,
      left: `${x}px`,
    }"
  />
</template>

<script>
export default {
  name: 'Location',

  props: {
    type: { type: String, required: true },
    x: { type: Number, required: true },
    y: { type: Number, required: true },
  },
}
</script>
