<script setup>
import pageData from '@/data/index.json'
import AboutSection from '@/components/AboutSection.vue' // importante!

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
  </Container>
</template>
