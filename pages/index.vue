<script setup>
import pageData from '@/data/index.json'
import AboutSection from '@/components/AboutSection.vue'
import Hero from '@/components/Hero.vue'
import Logos from '@/components/Logos.vue'
import Features from '@/components/Features.vue'
import Testimonials from '@/components/Testimonials.vue'
import Cta from '@/components/Cta.vue'
import CtaAventura from '@/components/CtaAventura.vue' // novo bloco

const page = ref(pageData)

definePageMeta({
  layout: "default",
});
</script>

<template>
  <Container>
    <Hero
      :title="page.hero.title"
      :description="page.hero.description"
      :image="page.hero.image"
      :imageAlt="page.hero.imageAlt"
      :buttons="page.hero.buttons"
    />

    <AboutSection
      :title="page.about.title"
      :description="page.about.description"
    />

    <Logos :title="page.logos.title" :icons="page.logos.icons" />
    <Features
      :title="page.features.title"
      :description="page.features.description"
      :items="page.features.items"
    />
    <Testimonials
      :title="page.testimonials.title"
      :description="page.testimonials.description"
      :items="page.testimonials.items"
    />
    <Cta
      :title="page.cta.title"
      :description="page.cta.description"
      :buttons="page.cta.buttons"
    />

    <!-- Novo bloco CTA da aventura -->
    <CtaAventura
      :title="page.ctaAventura.title"
      :description="page.ctaAventura.description"
      :background="page.ctaAventura.background"
      :buttons="page.ctaAventura.buttons"
    />
  </Container>
</template>
