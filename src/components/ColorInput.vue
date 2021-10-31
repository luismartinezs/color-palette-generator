<template>
  <!-- Use input[type="color"] as it is already built in the browser -->
  <!-- Apply some tailwind classes -->
  <input
    class="w-8 h-8 rounded shadow cursor-pointer overflow-hidden"
    type="color"
    :value="color"
    @change="handleChange"
  />
</template>

<script>
export default {
  name: 'ColorInput',
  // takes reactive value as a prop
  props: {
    color: {
      type: String,
      default: '#000000',
    },
  },
  // emits updates on reactive value
  emits: ['update:color'],
  setup(_, { emit }) {
    // input event will trigger every time we click on the color picker
    // change event will only trigger when we close the color picker in any way (when the input loses focus)
    const handleChange = (event) => {
      // New color in hex format is emitted
      emit('update:color', event.target.value)
    }

    return {
      handleChange,
    }
  },
}
</script>

<style scoped>
/* Remove default browser styles to make the input look like a swatch */
/* https://www.codegrepper.com/code-examples/css/input+color+custom */
input[type='color'] {
  -webkit-appearance: none;
  border: none;
  width: 32px;
  height: 32px;
}
input[type='color']::-webkit-color-swatch-wrapper {
  padding: 0;
}
input[type='color']::-webkit-color-swatch {
  border: none;
}
</style>