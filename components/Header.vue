<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)
const openSubmenu = ref('')

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const toggleSubmenu = (label) => {
  openSubmenu.value = openSubmenu.value === label ? '' : label
}

const navOptions = [
  {
    label: "Home",
    children: [
      { label: "Header Static" },
      { label: "Header Slider" },
      { label: "Youtube Background" },
      { label: "Self Hosted Video" },
      { label: "RTL" }
    ]
  },
  {
    label: "Pages",
    children: [
      { label: "About" },
      { label: "Blog" },
      { label: "Blog Detail" },
      { label: "Researches" },
      { label: "Research Detail" },
      { label: "Contact" },
      { label: "Starter" }
    ]
  },
  {
    label: "Components",
    children: [
      { label: "Alerts" },
      { label: "Background" },
      { label: "Badges" },
      { label: "Breadcrumb" },
      { label: "Buttons" },
      { label: "Cards" },
      { label: "Carousel" },
      { label: "Collapse" },
      { label: "Dropdowns" },
      { label: "Fancyscroll" },
      { label: "Forms" },
      { label: "Hoverbox" },
      { label: "List group" },
      { label: "Modals" },
      { label: "Media object" },
      { label: "Navs" },
      { label: "Navbar" },
      { label: "Page headers" },
      { label: "Pagination" },
      { label: "Popovers" },
      { label: "Progress" },
      { label: "Scrollspy" },
      { label: "Spinners" },
      { label: "Tables" },
      { label: "Tabs" },
      { label: "Tooltips" },
      { label: "Toasts" },
      { label: "Php ajax form" }
    ]
  },
  {
    label: "Utilities",
    children: [
      { label: "Borders" },
      { label: "Clearfix" },
      { label: "Close icon" },
      { label: "Colors" },
      { label: "Display" },
      { label: "Embed" },
      { label: "Flex" },
      { label: "Figures" },
      { label: "Grid" },
      { label: "Sizing" },
      { label: "Stretched link" },
      { label: "Spacing" },
      { label: "Typography" },
      { label: "Vertical align" },
      { label: "Visibility" }
    ]
  },
  {
    label: "Plugins",
    children: [
      { label: "Accordion" },
      { label: "Countup" },
      { label: "Fancyscroll" },
      { label: "Ytplayer" },
      { label: "Flexslider" }
    ]
  },
  {
    label: "Documentation",
    children: [
      { label: "Getting started" },
      { label: "File structure" },
      { label: "Customization" },
      { label: "Gulp" },
      { label: "RTL" },
      { label: "Plugins" },
      { label: "Changelog" }
    ]
  }
]
</script>

<template>
  <header class="relative shadow-sm">
    <!-- Gradient Background -->
    <div class="absolute inset-0 bg-gradient-diagonal"></div>
    
    <!-- Top Header Section -->
    <div class="container relative px-4 py-3 mx-auto">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <div class="flex items-center">
          <img src="../assets/images/logo.png" alt="Medicare Logo" class="h-9" />
        </div>

        <!-- Mobile Menu Button -->
        <button 
          class="p-2 text-gray-600 lg:hidden"
          @click="toggleMenu"
        >
          <Icon 
            :name="isMenuOpen ? 'ph:x-bold' : 'ph:list-bold'" 
            size="24"
          />
        </button>

        <!-- Contact Info - Hidden on Mobile -->
        <div class="items-center hidden space-x-10 text-sm text-gray-600 lg:flex">
          <!-- Address -->
          <div class="flex items-start space-x-2">
            <Icon
              name="map:postal-code"
              style="color: var(--primary-color)"
              size="24"
            />
            <div>
              <span class="text-[1rem] font-bold" style="color: var(--primary-color)">
                Address
              </span>
              <br />
              <span>
                5525 W Slauson Ave,<br />
                LA, CA 90056, USA
              </span>
            </div>
          </div>

          <!-- Phone Appointment -->
          <div class="flex items-start space-x-2">
            <Icon
              name="stash:headphones-solid"
              style="color: var(--primary-color)"
              size="24"
            />
            <div>
              <span class="text-[1rem] font-bold" style="color: var(--primary-color)">
                Phone Appointment
              </span>
              <br />
              <span style="color: var(--primary-color)">
                (555) 555-1234<br />
                (555) 555-5678
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Navigation -->
    <nav class="text-white bg-primary">
      <div class="container px-4 mx-auto">
        <!-- Desktop Navigation -->
        <div class="hidden lg:block">
          <ul class="flex items-center">
            <li 
              v-for="(item, index) in navOptions" 
              :key="index"
              class="relative group"
            >
              <div class="flex items-center px-4 py-3 cursor-pointer nav-link-container">
                {{ item.label }}
                <Icon
                  name="stash:caret-down-light"
                  size="28"
                  class="ml-1 nav-dropdown-ele"
                />
              </div>
              <div 
                v-if="item.children"
                class="absolute left-0 hidden group-hover:block dropdown-menu"
              >
                <div 
                  :class="{
                    'grid grid-cols-4 gap-4 w-[800px]': item.label === 'Components',
                    'grid grid-cols-1 w-[240px]': item.label !== 'Components'
                  }"
                  class="p-6 bg-white rounded-lg shadow-lg dropdown-content"
                >
                  <a
                    v-for="(child, idx) in item.children"
                    :key="idx"
                    href="#"
                    class="px-4 py-2 text-gray-700 rounded-md hover:bg-gray-100 dropdown-item"
                  >
                    {{ child.label }}
                  </a>
                </div>
              </div>
            </li>
          </ul>
        </div>

        <!-- Mobile Navigation -->
        <div 
          :class="['lg:hidden transition-all', isMenuOpen ? 'block' : 'hidden']"
        >
          <ul class="py-2">
            <li 
              v-for="(item, index) in navOptions" 
              :key="index"
              class="border-b border-blue-900 last:border-none"
            >
              <button
                class="flex items-center justify-between w-full px-4 py-2 text-gray-200 hover:text-white"
                @click="toggleSubmenu(item.label)"
              >
                {{ item.label }}
                <Icon
                  name="stash:caret-down-light"
                  size="28"
                  :class="['transform transition-transform', 
                    openSubmenu === item.label ? 'rotate-180' : '']"
                />
              </button>
              <div 
                v-if="item.children && openSubmenu === item.label"
                :class="{
                    'grid grid-cols-4 gap-4': item.label === 'Components',
                    'grid grid-cols-1 ': item.label !== 'Components'
                  }"
                  class="p-6 bg-white rounded-lg shadow-lg dropdown-content"
                >
                <a
                  v-for="(child, idx) in item.children"
                  :key="idx"
                  href="#"
                   class="px-4 py-2 text-gray-700 rounded-md hover:bg-gray-100"
                >
                  {{ child.label }}
                </a>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
/* Gradient Background */
.bg-gradient-diagonal {
  background: linear-gradient(55deg, #ffffff 50%, #f4f8fc 50%);
  clip-path: polygon(0 0, 100% 0, 100% 100%, 0 70%);
  height: 100%;
  width: 100%;
  z-index: -1;
}

/* Navbar Styles */
.nav-link-container {
  color: #ffffffb3;
}

.nav-link-container:hover {
  color: #ffffff;
}

/* Dropdown Menu */
.dropdown-menu {
  margin-top: 0.5rem;
  z-index: 50;
}

/* Primary Background */
.bg-primary {
  background-color: #0a3d75;
}

/* Dropdown Items */
.dropdown-item {
  transition: all 0.2s ease;
}

.dropdown-item:hover {
  color: var(--primary-color);
}

/* Transition for mobile menu */
.transition-all {
  transition: all 0.3s ease-in-out;
}
</style>