<script setup>
const centers = [
  {
    title: "Cancer Center",
    link: "#"
  },
  {
    title: "Orthopedic center",
    link: "#"
  },
  {
    title: "Heart and vascular center",
    link: "#"
  },
  {
    title: "The lung center",
    link: "#"
  },
  {
    title: "Neuroscience center",
    link: "#"
  },
  {
    title: "Women Health Center",
    link: "#"
  },
  {
    title: "Primary Care Center",
    link: "#"
  },
  {
    title: "All Departments & services",
    link: "#"
  }
];
</script>

<template>
  <div class="relative px-4 py-20 excellence-section">
    <div class="container max-w-6xl mx-auto">
      <!-- Header -->
      <div class="mb-16 text-center">
        <p class="mb-2 text-sm tracking-wide text-white">All Centers</p>
        <h2 class="text-4xl font-bold tracking-wide text-white">CENTERS OF EXCELLENCE</h2>
        <div class="w-16 h-0.5 bg-white mx-auto mt-4"></div>
      </div>

      <!-- Centers Grid -->
      <div class="grid grid-cols-1 gap-6 mb-16 md:grid-cols-2 lg:grid-cols-3">
        <a 
          v-for="center in centers" 
          :key="center.title"
          :href="center.link"
          class="center-card group"
        >
          <div class="flex items-center justify-between">
            <span class="text-lg font-medium text-white">{{ center.title }}</span>
            <svg 
              xmlns="http://www.w3.org/2000/svg" 
              class="w-6 h-6 text-white transition-transform transform group-hover:translate-x-2" 
              fill="none" 
              viewBox="0 0 24 24" 
              stroke="currentColor"
            >
              <path 
                stroke-linecap="round" 
                stroke-linejoin="round" 
                stroke-width="2" 
                d="M9 5l7 7-7 7" 
              />
            </svg>
          </div>
        </a>
      </div>

      <!-- Bottom Text -->
      <div class="max-w-4xl mx-auto text-center">
        <p class="text-lg leading-relaxed text-white">
          Although there is no magic formula for a long, healthy life, decades of 
          research confirm certain behaviors improve your chances. After 43 
          years, The Nurses' Health Study continues to find new insights for 
          maintaining a healthy lifestyle.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>


.excellence-section {
  background:
              url('../assets/images/excellence.png') center/cover no-repeat;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.center-card {
  padding: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 4px;
  transition: all 0.3s ease;
  background: rgba(255, 255, 255, 0.05);
}

.center-card:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

/* Font settings */
h2 {
  font-family: 'Arial', sans-serif;
  letter-spacing: 0.05em;
}

.text-white {
  color: rgba(255, 255, 255, 0.95);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .excellence-section {
    padding: 4rem 1rem;
  }
  
  h2 {
    font-size: 1.875rem;
  }
  
  .center-card {
    padding: 1.25rem;
  }
}
</style>