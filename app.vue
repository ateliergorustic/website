<script lang="ts" setup>
useSeoMeta({
  title: 'My Amazing Site',
  ogTitle: 'My Amazing Site',
  description: 'This is my amazing site, let me tell you all about it.',
  ogDescription: 'This is my amazing site, let me tell you all about it.',
  ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})

const mainRef = ref<HTMLElement>()

onMounted(() => {
  if(mainRef.value) {
    const text = mainRef.value.innerText.split('')

    const rewrite = text.map((ele, index) => `<span class="text-animate" style="${ele !== ' ' && 'display: inline-block;'} animation-delay: ${0.1 * index}s">${ele}</span>`).join('')

    mainRef.value.innerHTML = rewrite
  }
})
</script>

<template>
  <div class="w-100vw h-100vh flex items-center justify-center">
    <h1 ref="mainRef" class="text-8vw">Coming soon</h1>
  </div>
</template>

<style lang="scss">
.text-animate {
  animation: text-animate 1s ease infinite;
}

@keyframes text-animate {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20%);
  }
  100% {
    transform: translateY(0%);
  }
}
</style>