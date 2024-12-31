<script setup>
import { ref } from "vue";

import helpingPatient1 from "../assets/images/helpingpatient1.png";
import helpingPatient2 from "../assets/images/helpingpatient2.png";
</script>

<template>
  <div class="px-8 py-10 bg-white">

    <div class="mb-16 text-center">
        <p class="mb-2 text-sm tracking-wide text-blue-900">Brigham Health</p>
        <h2 class="mb-2 text-2xl font-bold text-center text-blue-900">HELPING OUR PATIENTS</h2>
        <!-- <div class="z-10 w-16 h-0.5 mx-auto mt-4 bg-blue-900"></div> -->
         <hr class="">
      </div>
      
    <!-- Main Section -->
    <div class="grid grid-cols-1 gap-8 md:grid-cols-3">
      <!-- Left Section -->
      <div>
        <div class="p-6 bg-gray-100 rounded-lg shadow-md">
          <h3 class="mb-6 text-lg font-bold text-blue-900">
            HOW CAN WE HELP YOU?
          </h3>
          <div class="space-y-4">
            <button
              class="flex items-center justify-between w-full px-4 py-3 text-sm font-medium text-white transition duration-300 bg-blue-900 rounded-lg hover:bg-blue-500"
            >
              Find a Doctor
              <span class="text-lg font-bold text-white">&gt;</span>
            </button>
            <button
              class="flex items-center justify-between w-full px-4 py-3 text-sm font-medium text-white transition duration-300 bg-blue-900 rounded-lg hover:bg-blue-500"
            >
              Request Appointment
              <span class="text-lg font-bold text-white">&gt;</span>
            </button>
            <button
              class="flex items-center justify-between w-full px-4 py-3 text-sm font-medium text-white transition duration-300 bg-blue-900 rounded-lg hover:bg-blue-500"
            >
              Location
              <span class="text-lg font-bold text-white">&gt;</span>
            </button>
            <button
              class="flex items-center justify-between w-full px-4 py-3 text-sm font-medium text-white transition duration-300 bg-blue-900 rounded-lg hover:bg-blue-500"
            >
              Services
              <span class="text-lg font-bold text-white">&gt;</span>
            </button>
          </div>
        </div>
      </div>

      <!-- Right Section -->
      <div class="space-y-8 md:col-span-2">
        <!-- Cards Section -->
        <div class="grid grid-cols-1 gap-8 md:grid-cols-2">
          <div class="overflow-hidden bg-white rounded-lg shadow-md hvr-shadow">
            <img
              :src="helpingPatient1"
              alt="Doctors"
              class="object-cover w-full h-48"
            />
            <div class="p-4">
              <h4 class="mb-2 text-lg font-bold text-blue-900 hover:text-black">
                Brigham Health Physicians Named 'Top Doctors'
              </h4>
              <p class="mb-4 text-sm text-gray-700">
                More than 275 Brigham Health physicians were included on Boston
                magazine's 2019 list of "Top Doctors." To prepare the annual
                list, Boston magazine partners with Castle Connolly Medical.
              </p>
              <a
                href="#"
                class="text-sm font-medium text-blue-900 hover:underline"
              >
                Learn More &gt;
              </a>
            </div>
          </div>

          <div class="overflow-hidden bg-white rounded-lg shadow-md hvr-shadow">
            <img
              :src="helpingPatient2"
              alt="Healthcare"
              class="object-cover w-full h-48"
            />
            <div class="p-4">
              <h4 class="mb-2 text-lg font-bold text-blue-900 hover:text-black">
                BWH Named to US News & World Report's Honor Roll
              </h4>
              <p class="mb-4 text-sm text-gray-700">
                Brigham and Women’s Hospital has ranked among the top 20 best
                hospitals in the nation on US News and World Report’s Honor
                Roll.
              </p>
              <a
                href="#"
                class="text-sm font-medium text-blue-900 hover:underline"
              >
                Learn More &gt;
              </a>
            </div>
          </div>
        </div>

        <!-- Latest News Section -->
        <div class="p-6 bg-white rounded-lg shadow-md">
          <h3 class="mb-4 text-lg font-bold text-blue-900">LATEST NEWS</h3>
          <ul class="pl-6 space-y-2 text-sm text-gray-700 list-disc">
            <li>
              Scientists create molecular tool to remove toxic protein from
              neuronal models of dementia.
            </li>
            <li>
              Older women benefit significantly when screened with 3-D
              mammography.
            </li>
            <li>
              Public announcement concerning a proposed health care project.
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.hvr-shadow {
    -webkit-transition: all .2s ease-in-out;
    -o-transition: all .2s ease-in-out;
    transition: all .2s ease-in-out
}

.hvr-shadow:focus,.hvr-shadow:hover {
    -webkit-box-shadow: 0 7px 14px 0 rgba(59,65,94,.1),0 3px 6px 0 rgba(0,0,0,.07);
    box-shadow: 0 7px 14px 0 rgba(59,65,94,.1),0 3px 6px 0 rgba(0,0,0,.07);
    -webkit-transform: translateY(-.125rem);
    -ms-transform: translateY(-.125rem);
    transform: translateY(-.125rem)
}

</style>
