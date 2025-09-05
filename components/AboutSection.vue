<template>
  <section class="my-20 max-w-3xl mx-auto">
    <h2 class="text-3xl font-bold text-zinc-800 mb-6 text-center">{{ title }}</h2>
    <div class="text-lg text-zinc-600 space-y-4">
      <template v-for="(line, index) in lines" :key="index">
        <p v-if="!line.startsWith('-')">{{ line }}</p>
        <ul v-else>
          <li>{{ line.replace('-', '').trim() }}</li>
        </ul>
      </template>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: String,
  description: String
})

// Divide a descrição em linhas usando \n
const lines = computed(() => props.description.split('\n'))
</script>

