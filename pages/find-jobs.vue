<template>
  <div class="flex flex-col min-h-screen {{ job.bg }}">

    <!-- Hero Section -->
    <section class=" {{ job.bg }} from-white via-gray-50 to-gray-100 text-center p-7 pt-30">
      <div class="max-w-5xl mx-auto">
        <h1 class="text-4xl sm:text-5xl md:text-6xl font-extrabold text-gray-900 mb-4 tracking-tight">
          Find <span class="text-red-600">Jobs</span>
        </h1>

        <p class="text-xl sm:text-2xl md:text-3xl text-gray-700 font-semibold mb-6">
          With <span class="text-red-600 font-black tracking-wide">PeopleCore</span> Solutions
        </p>

        <p class="text-lg md:text-xl text-gray-600 mb-10 max-w-3xl mx-auto">
          PeopleCore is the only site you'll need to find your next job.
        </p>

        <!-- Search Filters -->
        <div class="flex flex-col sm:flex-row gap-4 max-w-4xl mx-auto bg-white p-5 md:p-6 rounded-2xl shadow-xl border border-gray-200">

          <!-- Location -->
          <div class="relative flex-1 min-w-[200px]">
            <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none z-10">
              <svg class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </div>

            <select
              v-model="selectedLocation"
              class="w-full pl-11 pr-10 py-3.5 border border-gray-300 rounded-lg focus:ring-2 focus:ring-red-500 focus:border-red-500 bg-white appearance-none shadow-sm transition cursor-pointer hover:border-gray-400"
              :class="{ 'text-gray-900': selectedLocation, 'text-gray-500': !selectedLocation }"
            >
              <option value="">Location...</option>
              <option value="Phnom Penh">Phnom Penh</option>
              <option value="Siem Reap">Siem Reap</option>
              <option value="All Cambodia">All Cambodia</option>
            </select>

            <div class="absolute inset-y-0 right-0 pr-3 flex items-center pointer-events-none">
              <svg class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </div>
          </div>

          <!-- Search Input -->
          <div class="relative flex-[2]">
            <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
              <svg class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
              </svg>
            </div>
            <input
              v-model="searchQuery"
              type="text"
              placeholder="Search by jobs or companies..."
              class="w-full pl-11 pr-4 py-3.5 border border-gray-300 rounded-lg focus:ring-2 focus:ring-red-500 focus:border-red-500 text-gray-900 placeholder-gray-400"
              @keyup.enter="handleSearch"
            />
          </div>

          <!-- Search Button -->
          <button
            @click="handleSearch"
            class="bg-red-600 hover:bg-red-700 text-white font-semibold py-3.5 px-10 rounded-lg transition shadow-md whitespace-nowrap text-base"
          >
            Search Jobs
          </button>
        </div>
      </div>
    </section>

    <!-- Featured Jobs Carousel -->
    <main class="flex-grow py-12 px-5 md:px-8 lg:px-12 bg-gray-100">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mb-8 text-center md:text-left pl-3">
          Featured Jobs
        </h2>

        <div class="relative overflow-hidden" @mouseenter="pauseAutoSlide = true" @mouseleave="pauseAutoSlide = false">
          <!-- Slider Track -->
          <div class="flex transition-transform duration-700 ease-in-out"
            :style="{ transform: `translateX(-${currentIndex * (100 / visibleCards)}%)` }">
            <div
               v-for="(job, idx) in filteredJobs || []"
               
              :key="index"
              class="flex-shrink-0 px-3"
              :style="{ flex: `0 0 ${100 / visibleCards}%` }"
            >
              <AppJobCard
                :title="job.title"
                :company="job.company"
                :location="job.location"
                :salary="job.salary"
                :image="job.image"
                :bg="job.bg"
              />
            </div>
          </div>

          <!-- Arrows -->
          <button
            @click="prevSlide"
            class="absolute left-0 top-1/2 -translate-y-1/2 bg-white/80 hover:bg-white text-gray-800 p-3 rounded-full shadow-lg z-10 transition opacity-70 hover:opacity-100"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
            </svg>
          </button>

          <button
            @click="nextSlide"
            class="absolute right-0 top-1/2 -translate-y-1/2 bg-white/80 hover:bg-white text-gray-800 p-3 rounded-full shadow-lg z-10 transition opacity-70 hover:opacity-100"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
            </svg>
          </button>

          <!-- Dots -->
          <div class="flex justify-center mt-6 space-x-3">
            <button
              v-for="n in Math.ceil(jobs.length / visibleCards)"
              :key="n"
              @click="currentIndex = (n - 1) * visibleCards"
              :class="[
                'w-3 h-3 rounded-full transition-all',
                currentIndex >= (n-1)*visibleCards && currentIndex < n*visibleCards 
                  ? 'bg-red-600 scale-125' 
                  : 'bg-gray-400 hover:bg-gray-600'
              ]"
            />
          </div>
        </div>
      </div>
    </main>

    <!-- Job Cards Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 p-4 {{ job.bg }}">
      <div
        v-for="(job, idx) in filteredJobs"
        :key="idx"
        class="{{ job.bg }} rounded-2xl border border-gray-200 shadow-sm p-6 flex flex-col justify-between hover:shadow-md transition"
      >
        <div>
          <div class="flex justify-between items-center">
            <div class="flex items-center gap-3">
              <div class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center font-semibold ">
                {{ job.logo }}
              </div>
              <span class="text-gray-700 font-medium">{{ job.company }}</span>
            </div>
            <button class="w-9 h-9 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-100 transition">
              ♡
            </button>
          </div>

          <h2 class="mt-4 text-lg font-semibold text-gray-900">
            {{ job.title }} ({{ job.time }})
          </h2>
          <p class="mt-1 text-gray-600">{{ job.salary }}</p>

          <div class="grid grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm text-gray-600">
            <div>
              <span class="block text-xs text-gray-400">Office</span>{{ job.office }}
            </div>
            <div>
              <span class="block text-xs text-gray-400">Location</span>{{ job.location }}
            </div>
            <div>
              <span class="block text-xs text-gray-400">Closing Date</span>{{ job.closingDate }}
            </div>
            <div>
              <span class="block text-xs text-gray-400">Employment</span>{{ job.employment }}
            </div>
          </div>
        </div>

<NuxtLink
  :to="`/jobs/${job.id}`"
  class="mt-6 w-full py-3 rounded-full border border-red-500 text-red-500 font-medium hover:bg-red-500 hover:text-white transition text-center block"
>
  View More
</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
import axios from 'axios'
import { ref, computed, onMounted, onUnmounted } from 'vue'
import AppJobCard from '/components/AppJobCard.vue'

/* =========================
   STATE
========================= */
const jobs = ref([])
const loading = ref(false)
const error = ref(null)

const currentIndex = ref(0)
const pauseAutoSlide = ref(false)
const searchQuery = ref('')
const selectedLocation = ref('')
const visibleCards = ref(4)

let interval = null
const API_URL = 'http://localhost:1337'

/* =========================
   SAFE DATA MAPPER
   (WORKS FOR STRAPI v4 + v5)
========================= */
const normalizeJob = (item) => {
  const data = item.attributes ? item.attributes : item

  return {
    id: item.id,
    title: data?.title || '',
    company: data?.company || '',
    location: data?.location || '',
    salary: data?.salary || '',
    employment: data?.employment || '',
    closingDate: data?.closingDate || '',
    office: data?.office || '',
    time: data?.employment || '',
    logo: data?.company ? data.company.charAt(0).toUpperCase() : 'J',
    image: '',
    bg: 'bg-red-600'
  }
}

/* =========================
   FETCH JOBS
========================= */
const fetchJobs = async () => {
  loading.value = true
  error.value = null

  try {
    const response = await axios.get(`${API_URL}/api/jobs`)
    console.log("API RESPONSE:", response.data)

    if (!response.data?.data) {
      jobs.value = []
      return
    }

    jobs.value = response.data.data.map(normalizeJob)

  } catch (err) {
    console.error(err)
    error.value = "Failed to load jobs"
    jobs.value = []
  } finally {
    loading.value = false
  }
}

/* =========================
   SEARCH (SAFE VERSION)
========================= */
const handleSearch = async () => {
  currentIndex.value = 0
  fetchJobs()
}

/* =========================
   RESPONSIVE CAROUSEL
========================= */
const updateVisibleCards = () => {
  if (window.innerWidth < 640) visibleCards.value = 1
  else if (window.innerWidth < 1024) visibleCards.value = 2
  else visibleCards.value = 4
}

const nextSlide = () => {
  if (!jobs.value.length) return

  if (currentIndex.value < jobs.value.length - visibleCards.value)
    currentIndex.value += visibleCards.value
  else
    currentIndex.value = 0
}

const prevSlide = () => {
  if (!jobs.value.length) return

  if (currentIndex.value > 0)
    currentIndex.value -= visibleCards.value
  else
    currentIndex.value = Math.max(0, jobs.value.length - visibleCards.value)
}

const startAutoSlide = () => {
  interval = setInterval(() => {
    if (!pauseAutoSlide.value) nextSlide()
  }, 5000)
}

/* =========================
   LIFECYCLE
========================= */
onMounted(() => {
  updateVisibleCards()
  window.addEventListener('resize', updateVisibleCards)
  fetchJobs()
  startAutoSlide()
})

onUnmounted(() => {
  window.removeEventListener('resize', updateVisibleCards)
  if (interval) clearInterval(interval)
})

/* =========================
   FRONTEND FILTER (BACKUP)
========================= */
const filteredJobs = computed(() => {
  if (!jobs.value.length) return []

  return jobs.value.filter(job => {
    const matchesQuery =
      job.title.toLowerCase().includes(searchQuery.value.toLowerCase()) ||
      job.company.toLowerCase().includes(searchQuery.value.toLowerCase())

    const matchesLocation =
      selectedLocation.value === '' ||
      job.location === selectedLocation.value

    return matchesQuery && matchesLocation
  })
})
</script>