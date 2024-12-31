<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

import Carosol1 from "../assets/images/carosol1.png";
import Carosol2 from "../assets/images/carosol2.png";
import Carosol3 from "../assets/images/caroso3.png";

const slides = [
  {
    title: "One Stop Solution",
    subtitle: "Medical services",
    description: "Call to schedule an appointment today",
    buttonText: "Learn More",
    image: Carosol1,
  },
  {
    title: "Expert Healthcare",
    subtitle: "Professional Team",
    description: "Get the best medical care from our specialists",
    buttonText: "Book Now",
    image: Carosol2,
  },
  {
    title: "Modern Facilities",
    subtitle: "Advanced Technology",
    description: "State-of-the-art medical equipment and facilities",
    buttonText: "Discover More",
    image: Carosol3,
  },
];

const currentSlide = ref(0);
const autoplayInterval = ref(null);

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length;
};

const prevSlide = () => {
  currentSlide.value =
    currentSlide.value === 0 ? slides.length - 1 : currentSlide.value - 1;
};

const startAutoplay = () => {
  autoplayInterval.value = setInterval(nextSlide, 5000);
};

const stopAutoplay = () => {
  if (autoplayInterval.value) {
    clearInterval(autoplayInterval.value);
  }
};

onMounted(() => {
  startAutoplay();
});

onBeforeUnmount(() => {
  stopAutoplay();
});
</script>

<template>
  <div class="relative w-full h-[600px] overflow-hidden">
    <!-- Slides -->
    <div
      v-for="(slide, index) in slides"
      :key="index"
      class="absolute inset-0 w-full h-full transition-opacity duration-1000"
      :class="{ 'opacity-0': currentSlide !== index }"
    >
      <!-- Background Image -->
      <div
        class="absolute inset-0 w-full h-full bg-center bg-cover"
        :style="{ backgroundImage: `url(${slide.image})` }"
      >
        <!-- <div class="absolute inset-0 bg-black bg-opacity-40"></div> -->
      </div>

      <!-- Content -->
      <div class="container relative h-full px-6 mx-auto">
        <div
          class="flex flex-col justify-center h-full max-w-2xl text-white"
          :class="{ 'animate-slide-in': currentSlide === index }"
        >
          <h2
            class="mb-2 text-5xl font-bold transition-transform duration-1000 transform"
            :class="
              currentSlide === index
                ? 'translate-x-0 opacity-100'
                : '-translate-x-full opacity-0'
            "
          >
            {{ slide.title }}
          </h2>
          <h3
            class="mb-4 text-4xl text-blue-500 transition-transform duration-1000 delay-200 transform"
            :class="
              currentSlide === index
                ? 'translate-x-0 opacity-100'
                : '-translate-x-full opacity-0'
            "
          >
            {{ slide.subtitle }}
          </h3>
          <p
            class="mb-8 text-xl transition-transform duration-1000 transform delay-400"
            :class="
              currentSlide === index
                ? 'translate-x-0 opacity-100'
                : '-translate-x-full opacity-0'
            "
          >
            {{ slide.description }}
          </p>
          <button
            class="px-8 py-3 text-lg font-semibold text-white duration-300 transform bg-blue-600 rounded-md w-fit hover:bg-blue-700 delay-600"
            :class="
              currentSlide === index
                ? 'translate-x-0 opacity-100'
                : '-translate-x-full opacity-0'
            "
          >
            {{ slide.buttonText }}
          </button>
        </div>
      </div>
    </div>

    <!-- Navigation Buttons -->
    <div class="absolute flex space-x-2 bottom-8 right-8">
      <button
        v-for="(_, index) in slides"
        :key="index"
        @click="currentSlide = index"
        class="w-3 h-3 transition-all duration-300 rounded-full"
        :class="currentSlide === index ? 'bg-blue-600 w-8' : 'bg-white'"
      ></button>
    </div>

    <!-- Arrow Navigation -->
    <button
      @click="prevSlide"
      class="absolute p-2 text-white transition-all duration-300 -translate-y-1/2 rounded-full left-4 top-1/2 bg-white/10 hover:bg-white/20"
    >
      <Icon name="ph:caret-left-bold" size="24" />
    </button>
    <button
      @click="nextSlide"
      class="absolute p-2 text-white transition-all duration-300 -translate-y-1/2 rounded-full right-4 top-1/2 bg-white/10 hover:bg-white/20"
    >
      <Icon name="ph:caret-right-bold" size="24" />
    </button>
  </div>
</template>

<style scoped>
.animate-slide-in {
  animation: slide-in 1s ease-out;
}

@keyframes slide-in {
  from {
    transform: translateX(-100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* Ensure smooth transitions between slides */
.transition-opacity {
  transition-property: opacity;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
</style>
