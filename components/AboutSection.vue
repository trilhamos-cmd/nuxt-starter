<template>
  <section class="my-20 max-w-6xl mx-auto px-4">
    <!-- Título -->
    <h2 class="text-4xl font-bold text-yellow-500 text-center mb-12">{{ title }}</h2>

    <!-- Texto introdutório -->
    <div class="text-lg text-white leading-relaxed mb-8 text-justify">
      <p v-for="(line, index) in introLines" :key="'p-'+index">{{ line }}</p>
    </div>

    <!-- Lista em cards -->
    <div class="grid md:grid-cols-3 gap-6">
      <div
        v-for="(item, index) in listLines"
        :key="'card-'+index"
        class="bg-black border border-yellow-500 rounded-lg p-6 hover:shadow-xl transition-shadow"
      >
        <!-- Ícone do bullet -->
        <div class="text-yellow-500 mb-4 text-2xl">•</div>
        <p class="text-white text-base leading-relaxed">{{ item }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: String,
  description: String
})

// Divide o texto em linhas
const lines = computed(() => props.description.split('\n'))

// Separar introdução (linhas normais) e itens de lista
const introLines = computed(() => lines.value.filter(l => !l.startsWith('-')))
const listLines = computed(() =>
  lines.value.filter(l => l.startsWith('-')).map(l => l.replace('-', '').trim())
)
</script>

<style scoped>
section {
  background-color: #000; /* fundo preto */
  padding: 4rem 1rem;
  border-radius: 1rem;
}

p {
  color: #fff;
}

h2 {
  color: #FFD700; /* amarelo da identidade */
}
</style>
