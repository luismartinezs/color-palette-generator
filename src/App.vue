<script>
import FullScreen from '@/components/FullScreen.vue'

export default {
  name: "App",
  components: {
    FullScreen
  }
}

</script>

<template>
  <FullScreen>
      <router-view />
    </FullScreen>
</template>
