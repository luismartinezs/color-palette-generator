<template>
  <div class="flex space-x-1">
    <ColorInput
      v-for="(color, index) in colors"
      :key="index"
      :color="color"
      @update:color="value => updateColor(value, index)"
      class="shadow"
    />
  </div>
</template>

<script>
import { ref } from 'vue'
import ColorInput from '@/components/ColorInput.vue'

export default {
  components: {
    ColorInput
  },
  setup() {
    const colors = ref(Array(9).fill('#000000'))

    const updateColor = (color, index) => {
      colors.value[index] = color
    }

    return {
      colors,
      updateColor
    }
  }
}
</script>