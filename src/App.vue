<template>
  <div id="app">
    <TheHeader />
    <TheEditor />
  </div>
</template>

<script setup lang="ts">
import { useTelemetry } from '@/services/telemetry'

useTelemetry()
</script>

<style lang="scss" scoped>
#app {
  display: grid;
  grid-template-rows: var(--header-height) 1fr;
  height: 100vh;
}
</style>
