<script setup>
import pageData from '@/data/index.json'
import AboutSection from '@/components/AboutSection.vue'  // importante!
import Hero from '@/components/Hero.vue'
import Logos from '@/components/Logos.vue'
import Features from '@/components/Features.vue'
import Testimonials from '@/components/Testimonials.vue'
import Cta from '@/components/Cta.vue'

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
  </Container>
</template>
