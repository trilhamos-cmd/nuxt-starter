<template>
  <section class="my-20 max-w-3xl mx-auto px-4">
    <h2 class="text-3xl font-bold text-zinc-800 mb-6 text-center">{{ title }}</h2>
    <div class="text-lg text-zinc-600 space-y-4">
      <!-- Parágrafos normais -->
      <p v-for="(line, index) in normalLines" :key="'p-'+index">{{ line }}</p>

      <!-- Lista de itens iniciados com "-" -->
      <ul v-if="listLines.length" class="list-disc pl-6 space-y-2">
        <li v-for="(item, i) in listLines" :key="'li-'+i">{{ item }}</li>
      </ul>
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

// Separar linhas normais e itens de lista
const normalLines = computed(() => lines.value.filter(l => !l.startsWith('-')))
const listLines = computed(() => lines.value
  .filter(l => l.startsWith('-'))
  .map(l => l.replace('-', '').trim())
)
</script>
