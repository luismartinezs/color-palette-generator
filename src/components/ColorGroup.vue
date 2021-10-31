<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
import ColorInput from '@/components/ColorInput.vue'

export default {
  components: {
    ColorInput
  },
  props: {
    colorGroup: {
      type: Object,
      required: true
    }
  }
}
</script>