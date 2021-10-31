<script>
import FullScreen from '@/components/FullScreen.vue'
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import BackgroundWrapper from './components/BackgroundWrapper.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    FullScreen,
    DefaultLayout,
    BackgroundWrapper,
    TheHeader
  }
}
</script>

<template>
  <FullScreen>
    <BackgroundWrapper>
      <DefaultLayout>
        <template #header>
          <TheHeader />
        </template>
        <template #content>
          <router-view />
        </template>
      </DefaultLayout>
    </BackgroundWrapper>
  </FullScreen>
</template>
