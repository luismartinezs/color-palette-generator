<template>
  <ColorGroup
    v-for="(colorGroup, colorGroupIdx) in scheme"
    :key="colorGroup.label"
    :colorGroup="colorGroup"
  >
    <div class="mb-3 capitalize text-gray-600">{{colorGroup.label}}</div>
    <div class="flex space-x-1 mb-4">
      <div
        v-for="(shade, shadeIdx) in colorGroup.shades"
        :key="`${colorGroup.label}${shade.label}`"
        class="flex flex-col items-center"
      >
        <ColorInput
          class="w-8 h-8 sm:w-10 sm:h-10 md:w-12 md:h-12 rounded shadow cursor-pointer overflow-hidden mb-1"
          :color="shade"
          @update:color="newColor => onUpdateColor(newColor, colorGroupIdx, shadeIdx)"
        />
        <div class="text-sm text-gray-500">{{shade.label}}</div>
      </div>
    </div>
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
            label: '100',
            value: '#e6e6e6'
          },
          {
            label: '200',
            value: '#cccccc'
          },
          {
            label: '300',
            value: '#b3b3b3'
          },
          {
            label: '400',
            value: '#999999'
          },
          {
            label: '500',
            value: '#808080'
          },
          {
            label: '600',
            value: '#666666'
          },
          {
            label: '700',
            value: '#4d4d4d'
          },
          {
            label: '800',
            value: '#333333'
          },
          {
            label: '900',
            value: '#1a1a1a'
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