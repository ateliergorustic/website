<script lang="ts" setup>
const title = "ATELIER GO RUSTIC";
const description =
  'Explore handcrafted home goods at Atelier GO RUSTIC, blending the serene aesthetics of "wabi-sabi" with natural materials and minimal human intervention. Discover our collection of artisanal pieces, meticulously crafted to harmonize with your living space and evoke tranquility.';
const keyword = [
  title,
  title.toLowerCase(),
  "Wabisabi style",
  "Quercus acutissima",
  "Weathered wood",
  // "Table tray",
  // "Imperfectus style",
  // "Pottery",
  // "Copper tea set",
  // "Handcrafted",
  // "Rustic style",
  // "Natural materials",
  // "Creative workshop",
  // "Handmade decor",
  // "Exquisite craftsmanship",
  // "Wood design",
  // "Natural aesthetics",
  // "Hand carving",
  // "Simple living",
  // "Handcrafted production",
  // "Primitive style",
];

useSeoMeta({
  title: title,
  ogTitle: title,
  description: description,
  ogDescription: description,
  twitterCard: "summary_large_image",
  keywords: keyword.join(","),
});

const mainRef = ref<HTMLElement>();

onMounted(() => {
  if (mainRef.value) {
    const text = mainRef.value.innerText.split("");

    const rewrite = text
      .map(
        (ele, index) =>
          `<span class="text-animate" style="${
            ele !== " " && "display: inline-block;"
          } animation-delay: ${0.1 * index}s">${ele}</span>`
      )
      .join("");

    mainRef.value.innerHTML = rewrite;
  }
});
</script>

<template>
  <div class="w-100vw h-100vh relative">
    <h1 class="text-center">{{ title }}</h1>

    <div class="absolute top-50% left-50% -translate-50% ws-nowrap">

      <strong ref="mainRef" class="text-8vw">Coming soon</strong>
    </div>
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
