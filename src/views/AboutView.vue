<script setup lang="ts">
import { TresCanvas } from '@tresjs/core'
// const props = defineProps({
//   foo: { type: String, required: true },
//   bar: Number
// })
const props = defineProps<{
  foo: string
  bar?: number
}>()

props.bar
props.foo

// const emit = defineEmits(['change', 'update'])

// const emit = defineEmits({
//   change: (id: number) => { },
//   update: (value: string) => { }
// })
// const emit = defineEmits<{
//   (e: 'change', id: number): void
//   (e: 'update', value: string): void
// }>()
const emit = defineEmits<{
  change: [id: number]
  update: [value: string]
}>()
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
