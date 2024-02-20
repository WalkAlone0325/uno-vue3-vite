<script setup lang="ts">
import { useGlobalState } from '@/stores/store'
import { breakpointsTailwind, useBreakpoints, useDateFormat, useDraggable, useNow, useParentElement, useStorage, useTimeAgo, useWindowSize } from '@vueuse/core'
import { onMounted } from 'vue'
import { ref } from 'vue'
// import TheWelcome from '../components/TheWelcome.vue'

const store = useGlobalState()

localStorage.setItem('my-state', '{ "hello": "hell0" }')

const state = useStorage('my-state', { hello: 'h1', greeting: 'Hello' }, localStorage, { mergeDefaults: true })
const flag = useStorage('my-flag', true)
const count = useStorage('my-count', 0)
const id = useStorage('my-id', 'some-string-id', sessionStorage)

console.log(state.value)

//
const el = ref<HTMLElement | null>(null)

const { x, y, style } = useDraggable(el, { initialValue: { x: 40, y: 40 } })

const parentEl = useParentElement()

onMounted(() => {
  console.log(parentEl.value)
})

const { width, height } = useWindowSize()

const breakpoints = useBreakpoints(breakpointsTailwind)
console.log(breakpoints)

const timeAgo = useTimeAgo(new Date(2021, 0, 1))

const nowTime = useNow()
const formatted = useDateFormat(nowTime, 'YYYY-MM-DD HH:mm')
</script>

<template>
  <main>
    {{ state }}
    {{ flag }}
    {{ count }} -- {{ typeof count }}
    {{ id }}
    <!-- <div>{{ store.count }}</div>
    <div>{{ store.doubleCount }}</div>
    <button @click="store.increment">++</button> -->

    <div ref="el" :style fixed b-green b-2 b-solid cursor-auto>
      Drag me ! I am at {{ x }}, {{ y }}
    </div>

    <div>
      width: {{ width }}
      height: {{ height }}
    </div>

    <div>
      {{ timeAgo }}
    </div>
    <div>{{ nowTime }}</div>
    <div>{{ formatted }}</div>
    <!-- <TheWelcome /> -->
  </main>
</template>
