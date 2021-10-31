<script>
import FullScreen from '@/components/FullScreen.vue'
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import BackgroundWrapper from '@/components/BackgroundWrapper.vue'
import TheHeader from '@/components/TheHeader.vue'
import WidthWrapper from '@/components/WidthWrapper.vue'
import HeightWrapper from './components/HeightWrapper.vue'

export default {
  name: 'App',
  components: {
    FullScreen,
    DefaultLayout,
    BackgroundWrapper,
    TheHeader,
    WidthWrapper,
    HeightWrapper
  }
}
</script>

<template>
  <FullScreen>
    <BackgroundWrapper>
      <DefaultLayout>
        <template #header>
          <div class="bg-blue-500 h-full">
            <WidthWrapper>
              <TheHeader />
            </WidthWrapper>
          </div>
        </template>
        <template #content>
          <WidthWrapper>
            <HeightWrapper>
              <router-view />
            </HeightWrapper>
          </WidthWrapper>
        </template>
      </DefaultLayout>
    </BackgroundWrapper>
  </FullScreen>
</template>
