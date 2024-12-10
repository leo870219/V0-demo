<template>
  <div class="bg-gray-50 shadow-md rounded-30px overflow-hidden transition-all duration-300 hover:shadow-lg flex flex-col min-h-[404px] max-w-[360px] max-h-100vh w-full">
    <div class="p-8 bg-gradient-to-br from-gray-50 to-white flex flex-col flex-grow">
      <!-- Star Rating -->
      <div class="flex gap-6px mb-6">
        <div v-for="star in 5" :key="star" class="text-#FFBF1C h-[20px]">
          <svg
            class="w-5 h-5 h-[20px]"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            />
          </svg>
        </div>
      </div>

      <!-- Testimonial Text -->
      <p class="text-gray-700 text-2xl font-normal leading-[33.6px] mb-6 flex-grow max-h-[calc(100vh-172px)] overflow-y-auto">
        {{ testimonial }}
      </p>

      <!-- Profile Section -->
      <div class="flex items-center gap-3">
        <img
          :src="`https://i.pravatar.cc/150?u=${name}`"
          :alt="name"
          class="w-10 h-10 rounded-full object-cover"
        />
        <div>
          <h3 class="font-bold text-gray-900 text-sm leading-[16.1px] mb-1">{{ name }}</h3>
          <p class="text-gray-600 text-xs font-normal leading-[13.8px]">{{ title }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  testimonial: {
    type: String,
    required: true
  },
  name: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  avatar: {
    type: String,
    required: true
  }
})
</script>