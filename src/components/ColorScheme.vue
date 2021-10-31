<template>
  <ColorGroup
    v-for="(colorGroup, colorGroupIdx) in scheme"
    :key="colorGroup.label"
    :colorGroup="colorGroup"
    class="flex space-x-1 mb-4"
  >
    <ColorInput
      class="w-8 h-8 rounded shadow cursor-pointer overflow-hidden"
      v-for="(shade, shadeIdx) in colorGroup.shades"
      :key="`${colorGroup.label}${shade.label}`"
      :color="shade"
      @update:color="newColor => onUpdateColor(newColor, colorGroupIdx, shadeIdx)"
    />
  </ColorGroup>
</template>

<script>
import { ref } from 'vue'
import ColorGroup from '@/components/ColorGroup.vue'
import ColorInput from '@/components/ColorInput.vue'

export default {
  components: {
    ColorGroup,
    ColorInput
  },
  setup() {
    const scheme = ref([
      {
        label: 'primary',
        shades: [
          {
            label: '50',
            value: '#000000'
          },
          {
            label: '100',
            value: '#ffffff'
          }
        ]
      },
      {
        label: 'secondary',
        shades: [
          {
            label: '50',
            value: '#ffffff'
          }
        ]
      }
    ])

    const onUpdateColor = (newColor, colorGroupIdx, shadeIdx) => {
      scheme.value[colorGroupIdx].shades[shadeIdx].value = newColor
    }

    return {
      scheme,
      onUpdateColor
    }
  }
}
</script>