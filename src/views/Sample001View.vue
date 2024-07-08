<script setup>
import anime from 'animejs/lib/anime.es.js'
import { onMounted } from 'vue'

onMounted(() => {
  const mainEle = document.getElementById('main')
  const ww = mainEle.clientWidth
  const wh = mainEle.clientHeight
  console.log('ww', ww)
  console.log('wh', wh)

  const eles = []
  for (var i = 0; i < 200; i++) {
    const divele = document.createElement('div')
    divele.setAttribute('class', 'box')
    mainEle.appendChild(divele)
    eles.push(divele)
  }

  anime({
    targets: '.box',
    translateX: () => {
      return anime.random(0, mainEle.clientWidth / 1.2)
    },
    translateY: () => {
      return anime.random(0, mainEle.clientHeight / 1.2)
    },
    scaleX: () => {
      return anime.random(0.8, 1.2)
    },
    scaleY: () => {
      return anime.random(0.8, 1.2)
    },
    duration: 1000,
    delay: 1000
  })
})
</script>

<template>
  <div class="main" id="main"></div>
</template>

<style scoped>
.main {
  width: calc(100vw);
  height: calc(100vh);
  border: 1px red dashed;
  padding: 0;
  margin: 0;
  position: relative;
}
</style>
