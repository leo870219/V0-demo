<template>
  <div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-9 px-4">
      <TestimonialCard
        v-for="testimonial in testimonials"
        :key="testimonial.name"
        v-bind="testimonial"
      />
    </div>
  </div>
</template>

<script setup>
import TestimonialCard from './TestimonialCard.vue'

const testimonials = [
  {
    testimonial: "The goal was to find the right solution not just for our web team, but for the brand teams and everyone involved.",
    name: "Rebecca Doe",
    title: "Director of Brand Marketing",
    avatar: "/placeholder.svg?height=48&width=48"
  },
  {
    testimonial: "We feel like we've finally graduated up to something that has the flexibility we need and is all-around more scalable for everyone.",
    name: "John Doe",
    title: "Growth Manager",
    avatar: "/placeholder.svg?height=48&width=48"
  },
  {
    testimonial: "The goal was to find the right solution not just for our web team, but for the brand teams and everyone involved.",
    name: "Mark Doe",
    title: "VP of Product",
    avatar: "/placeholder.svg?height=48&width=48"
  }
]
</script>