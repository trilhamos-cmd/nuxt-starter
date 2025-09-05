<template>
  <section
    class="relative bg-cover bg-center py-24 px-6 text-center text-white"
    :style="{ backgroundImage: `url(${background})` }"
  >
    <div class="absolute inset-0 bg-black/60"></div>

    <div class="relative max-w-3xl mx-auto">
      <h2 class="text-4xl font-bold mb-6">{{ title }}</h2>
      <p class="text-lg mb-8">{{ description }}</p>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          v-for="(btn, index) in buttons"
          :key="index"
          :href="btn.link"
          target="_blank"
          rel="noopener"
          class="px-6 py-3 font-semibold rounded-lg transition duration-300"
          :class="btn.variant === 'yellow' 
            ? 'bg-yellow-400 text-black hover:bg-yellow-500' 
            : 'bg-black text-white hover:bg-zinc-800'"
        >
          {{ btn.label }}
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  buttons: { type: Array, required: true },
  background: { type: String, required: true }
})
</script>
