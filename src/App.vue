<template>
  <div class="container">
    <svg
      class="icon"
      :style="{ transform: `translate(${x}px, ${y}px)` }"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z" />
    </svg>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const size = 48
const speed = 0.7

const x = ref(0)
const y = ref(0)
let dx = speed
let dy = speed
let animId = null

function animate() {
  x.value += dx
  y.value += dy

  const maxX = window.innerWidth - size
  const maxY = window.innerHeight - size

  if (x.value <= 0 || x.value >= maxX) dx = -dx
  if (y.value <= 0 || y.value >= maxY) dy = -dy

  x.value = Math.max(0, Math.min(x.value, maxX))
  y.value = Math.max(0, Math.min(y.value, maxY))

  animId = requestAnimationFrame(animate)
}

onMounted(() => {
  x.value = Math.random() * (window.innerWidth - size)
  y.value = Math.random() * (window.innerHeight - size)
  animId = requestAnimationFrame(animate)
})

onUnmounted(() => cancelAnimationFrame(animId))
</script>

<style>
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  background: #000;
  color: #fff;
  overflow: hidden;
}

#app {
  height: 100%;
}

.container {
  position: relative;
  height: 100%;
}

.icon {
  position: absolute;
  top: 0;
  left: 0;
  width: 48px;
  height: 48px;
  opacity: 0.7;
  will-change: transform;
}
</style>
