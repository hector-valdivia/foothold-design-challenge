<template>
  <div class="container mx-auto">
    <div class="p-8">
      <img alt="Vue logo" src="./assets/logo.png" class="mx-auto" />
    </div>

    <div v-show="state.show" 
      class="fixed z-50 bottom-24 right-6 grid grid-cols-2 md:grid-cols-2 gap-2 transition duration-700 transform scale-80 w-3/4 md:w-2/3" style="max-width: 1020px;">
      <div v-for="(m, index) in menu" :key="index" 
        class="bg-white shadow-md hover:shadow-xl rounded-xl md:flex p-2 md:p-4">
        <div class="md:w-1/6">
          <img :src="`/svg/${m.svg}`" class="mx-auto h-10 md:w-full" />
        </div>
        <div class="md:w-5/6 pl-2 my-auto font-bold text-xs md:text-lg text-center md:text-left">
          {{ m.text }}
        </div>
      </div>
    </div>

    <div @click="state.show = !state.show" 
      class="fixed z-40 bottom-6 right-6 w-16 h-16 rounded-full shadow cursor-pointer" :class="{ 'bg-green-300': !state.show, 'bg-gray-900': state.show  }">
      <span class="sr-only">Open site navigation</span>

      <svg v-show="state.show" width="24" height="24" fill="none" stroke="white" class="absolute top-1/2 left-1/2 -mt-3 -ml-3 transition duration-300 transform scale-80">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
      </svg>

      <svg v-show="!state.show" width="24" height="24" fill="none" stroke="currentColor" class="absolute top-1/2 left-1/2 -mt-3 -ml-3 transition duration-300 transform">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
      </svg>
    </div>
  </div>
</template>

<script setup>

import { reactive } from 'vue'

const menu = [
  { svg: 'new_intakes.svg', text: 'New intake' },
  { svg: 'discharge.svg', text: 'Discharge' },
  { svg: 'check_in.svg', text: 'Check In' },
  { svg: 'check_out.svg', text: 'Check Out' },
  { svg: 'new_medication.svg', text: 'New medication' },
  { svg: 'new_treatment_plan.svg', text: 'New treatment plan' },
  { svg: 'new_incident.svg', text: 'New incident' },
  { svg: 'new_calendar_event.svg', text: 'New calendar event' },
  { svg: 'new_progress_note.svg', text: 'New progress note' },
  { svg: 'new_group_note.svg', text: 'New group note' },
]

const state = reactive({ show: false })

</script>

<style>
  #app {
    @apply font-sans;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>