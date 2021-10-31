<template>
  <header class="fixed z-20 top-0 left-0 right-0 h-14">
    <slot name="header"></slot>
  </header>
  <main class="block pb-8 pt-14">
    <slot name="content"></slot>
  </main>
</template>

<script>
export default {
  name: 'DashboardLayout'
}
</script>