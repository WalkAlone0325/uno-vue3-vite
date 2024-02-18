<script setup lang="ts">
import { TresCanvas } from '@tresjs/core'
</script>

<template>
  <div class="about">
    <TresCanvas shadows window-size>

    </TresCanvas>
  </div>
</template>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

#canvas {
  height: 100%;
  width: 100%;
}
</style>
