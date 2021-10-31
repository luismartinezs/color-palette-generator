<script>
import { ref } from 'vue'
import ColorInput from '@/components/ColorInput.vue'

export default {
  name: 'Home',
  components: {
    ColorInput
  },
  setup() {
    const color = ref('#000000')

    return { color }
  }
}
</script>

<template>
  <div>
    <ColorInput v-model:color="color" />
  </div>
</template>
