<template>
  <section
    class="relative bg-black text-white py-20 px-6 text-center overflow-hidden"
  >
    <!-- Fundo com imagem -->
    <div
      class="absolute inset-0 bg-cover bg-center opacity-40"
      :style="{ backgroundImage: `url(${backgroundImage})` }"
    ></div>

    <!-- Overlay escuro para contraste -->
    <div class="absolute inset-0 bg-black opacity-60"></div>

    <!-- Conteúdo -->
    <div class="relative z-10 max-w-3xl mx-auto">
      <h2 class="text-4xl font-bold mb-6">
        {{ title }}
      </h2>
      <p class="text-lg mb-8">
        {{ description }}
      </p>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          :href="telegramUrl"
          target="_blank"
          class="bg-yellow-400 text-black font-semibold px-6 py-3 rounded-xl shadow-md hover:bg-yellow-300 transition"
        >
          Entrar no Clube Trilhamos Telegram
        </a>
        <a
          :href="stravaUrl"
          target="_blank"
          class="bg-white text-black font-semibold px-6 py-3 rounded-xl shadow-md hover:bg-zinc-200 transition"
        >
          Entrar no Clube Trilhamos Strava
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: "Qual será sua próxima aventura?",
  },
  description: {
    type: String,
    default:
      "Entre para o Clube Trilhamos no Telegram e no Strava e descubra novas trilhas, troque experiências e faça parte da nossa comunidade.",
  },
  telegramUrl: {
    type: String,
    default: "https://t.me/seu-grupo", // substitua pelo link real
  },
  stravaUrl: {
    type: String,
    default: "https://www.strava.com/clubs/seu-grupo", // substitua pelo link real
  },
  backgroundImage: {
    type: String,
    default: "/images/trilha-fundo.jpg", // adicione essa imagem na pasta /public/images
  },
});
</script>

