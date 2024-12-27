<script setup>
import { ref } from 'vue'

const selectedLanguage = ref('en')

// Import country flags
import indiaFlag from '../assets/images/india.png';
import usaFlag from '../assets/images/usa.png';
import ukFlag from '../assets/images/uk.png';

// List of countries with flags
const countries = [
  { name: "India", code: "IN", flag: indiaFlag },
  { name: "USA", code: "US", flag: usaFlag },
  { name: "UK", code: "UK", flag: ukFlag },
];

// States
const isOpen = ref(false);
const selectedCountry = ref(countries[0]);

// Toggle dropdown visibility
const toggleDropdown = (event) => {
  isOpen.value = !isOpen.value;
  event.stopPropagation(); // Prevent closing the dropdown when clicked inside
};

// Select a country
const selectCountry = (country) => {
  selectedCountry.value = country;
  isOpen.value = false;
};

// Close dropdown when clicking outside
const closeDropdown = () => {
  isOpen.value = false;
};

// Add and remove event listeners
onMounted(() => {
  document.addEventListener('click', closeDropdown);
});

onUnmounted(() => {
  document.removeEventListener('click', closeDropdown);
});
</script>

<!-- components/NavBar.vue -->
<template>
  <nav class="bg-white shadow-md">
    <div class="container px-4 mx-auto">
      <div class="flex items-center justify-between h-16">
        <!-- Left side - Language selector -->
        <div class="dropdown-container">
    <!-- Dropdown Toggle -->
    <div
      @click="toggleDropdown"
      class="flex items-center gap-2 p-2 border rounded-lg cursor-pointer dropdown-selected"
    >
      <img :src="selectedCountry.flag" alt="Flag" class="w-6 h-6 rounded-full" />
      <!-- <span>{{ selectedCountry.name }}</span> -->
    </div>

    <!-- Dropdown Options -->
    <div v-if="isOpen" class="mt-2 bg-white border rounded-lg shadow-lg dropdown-options">
      <ul>
        <li
          v-for="country in countries"
          :key="country.code"
          @click="selectCountry(country)"
          class="flex items-center gap-2 p-2 cursor-pointer dropdown-option hover:bg-gray-100"
        >
          <img :src="country.flag" alt="Flag" class="w-6 h-6 rounded-full" />
          <span class = "dropdown-countryCode">{{ country.code }}</span>
        </li>
      </ul>
    </div>
  </div>

        <!-- Center - Search bar -->
        <div class="flex-1 hidden mx-8 md:block">
          <div class="relative">
            <input 
              type="text" 
              placeholder="Search..." 
              class="w-full max-w-md px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500"
            >
            <!-- <button class="absolute right-3 top-2.5 text-gray-400">
              🔍
            </button> -->
          </div>
        </div>

        <!-- Right side - Action buttons -->
        <div class="flex items-center space-x-2 md:space-x-4">
          <button class="px-3 py-2 text-sm text-red-500 border border-red-500 rounded-md md:px-4 hover:bg-red-400 md:text-base hover:text-white">
            <span class="hidden md:inline">Find a Doctor</span>
            <span class="md:hidden">Doctor</span>
          </button>
          <button class="px-3 py-2 text-sm text-white bg-blue-900 rounded-md md:px-4 hover:bg-blue-800 md:text-base">
            <span class="hidden md:inline">Request Appointment</span>
            <span class="md:hidden">Appointment</span>
          </button>
        </div>
      </div>

      <!-- Mobile search bar -->
      <div class="py-3 md:hidden">
        <div class="relative">
          <input 
            type="text" 
            placeholder="Search..." 
            class="w-full px-4 py-2 border rounded-md focus:outline-none focus:border-blue-500"
          >
          <button class="absolute right-3 top-2.5 text-gray-400">
            🔍
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.dropdown-container {
  width: auto;
  position: relative;
}

.dropdown-selected {
  background-color: white;
  border: 1px solid #ccc;
}

.dropdown-options {
  position: absolute;
  z-index: 1000;
  width: 120px; /* Set a larger width for options */
  left: 0; /* Align dropdown options */
}

.dropdown-option {
  display: flex;
  align-items: center;
  width: 100%; /* Ensure option items span full width */
}

.dropdown-countryCode {
  font-size: 10px;
}
</style>
