<template>
  <main class="h-screen w-full bg-gradient-to-br from-black to-[#0A0A1F] overflow-hidden relative">
    <!-- Top Icons Section -->
    <div class="absolute top-20 left-20 flex items-center gap-4">
      <div class="w-16 h-16 rounded-2xl bg-[#2D2D3D] flex items-center justify-center glow-purple">
        <img src="https://g-svasazdxcja.vusercontent.net/placeholder.svg?height=40&width=40" alt="Source icon" class="w-10 h-10" />
      </div>
      <div class="text-white text-2xl">→</div>
      <div class="w-16 h-16 rounded-2xl bg-[#2D2D3D] flex items-center justify-center glow-green">
        <img src="https://g-svasazdxcja.vusercontent.net/placeholder.svg?height=40&width=40" alt="Target icon" class="w-10 h-10" />
      </div>
    </div>

    <!-- Main Content -->
    <div class="container mx-auto px-4 pt-32 lg:pt-40 h-full flex flex-col justify-between relative z-10">
      <!-- Start Here Text -->
      <h2 class="text-[#CAFF00] text-2xl md:text-3xl font-medium mb-4">
        Start here
      </h2>

      <!-- Main Heading -->
      <h1 class="text-white text-5xl md:text-7xl font-bold max-w-3xl leading-tight">
        Using Figma to Code Plugin
      </h1>

      <!-- Floating Elements -->
      <div class="relative flex-grow mt-20">
        <!-- Gradient Card -->
        <div class="absolute right-[20%] top-0 w-64 h-96 rounded-2xl bg-gradient-to-br from-orange-400 to-purple-600 transform rotate-12 floating-element">
        </div>

        <!-- Code Window -->
        <div class="absolute left-[10%] bottom-20 w-96 h-64 bg-[#1E1E1E] rounded-xl p-4 floating-element-delayed">
          <div class="flex gap-2 mb-4">
            <div class="w-3 h-3 rounded-full bg-red-500"></div>
            <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
            <div class="w-3 h-3 rounded-full bg-green-500"></div>
          </div>
          <div class="text-green-400 font-mono text-sm">
            <div>const plugin = {</div>
            <div class="pl-4">name: 'figma-to-code',</div>
            <div class="pl-4">version: '1.0.0'</div>
            <div>}</div>
          </div>
        </div>

        <!-- Framework Icons -->
        <div class="absolute bottom-10 left-[40%] flex gap-4 floating-element">
          <div v-for="(icon, index) in ['react', 'vue', 'angular']" 
               :key="icon"
               class="w-12 h-12 rounded-lg bg-[#2D2D3D] flex items-center justify-center"
               :style="{ animationDelay: `${index * 0.2}s` }">
            <img :src="`https://g-svasazdxcja.vusercontent.net/placeholder.svg?height=30&width=30`" :alt="icon" class="w-8 h-8" />
          </div>
        </div>

        <!-- UI Cards -->
        <div class="absolute right-[10%] top-[20%] w-72 floating-element-delayed">
          <div class="bg-white rounded-xl p-4 mb-4 transform -rotate-6">
            <div class="h-4 w-3/4 bg-gray-200 rounded mb-2"></div>
            <div class="h-4 w-1/2 bg-gray-200 rounded"></div>
          </div>
          <div class="bg-white rounded-xl p-4 transform rotate-6">
            <div class="h-4 w-3/4 bg-gray-200 rounded mb-2"></div>
            <div class="h-4 w-1/2 bg-gray-200 rounded"></div>
          </div>
        </div>
      </div>
    </div>

    <!-- Background Grid -->
    <div class="absolute inset-0 bg-grid opacity-10"></div>
  </main>
</template>

<script setup>
// Component logic can be added here if needed
</script>

<style>
/* Grid background pattern */
.bg-grid {
  background-size: 50px 50px;
  background-image: 
    linear-gradient(to right, rgba(255,255,255,0.1) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(255,255,255,0.1) 1px, transparent 1px);
}

/* Glow effects */
.glow-purple {
  box-shadow: 0 0 30px rgba(147, 51, 234, 0.3);
}

.glow-green {
  box-shadow: 0 0 30px rgba(202, 255, 0, 0.3);
}

/* Floating animations */
.floating-element {
  animation: float 6s ease-in-out infinite;
}

.floating-element-delayed {
  animation: float 6s ease-in-out infinite;
  animation-delay: 1s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .floating-element,
  .floating-element-delayed {
    transform: scale(0.8);
  }
}

/* 確保內容在小螢幕上也能完全顯示 */
@media (max-height: 700px) {
  .container {
    padding-top: 1rem;
  }
  
  h1 {
    font-size: 2.5rem;
  }
  
  .floating-element,
  .floating-element-delayed {
    transform: scale(0.7);
  }
}

/* 調整超大螢幕的佈局 */
@media (min-height: 1000px) {
  .container {
    justify-content: center;
  }
}

/* Ensure smooth animations */
* {
  transition: all 0.3s ease;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

