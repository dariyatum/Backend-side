<template>
  <div class="flex flex-col min-h-screen bg-gray-50">
  

  
    <section class="bg-gradient-to-b from-white via-gray-50 to-gray-100 text-center p-7 pt-35">
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

        
        <div class="flex flex-col sm:flex-row gap-4 max-w-4xl mx-auto bg-white p-5 md:p-6 rounded-2xl shadow-xl border border-gray-200">
          
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
                <option value="">Location...</option>  <!-- No disabled/selected here -->

                <option value="Phnom Penh">Phnom Penh</option>
                <option value="Siem Reap">Siem Reap</option>
                <!-- ... other options ... -->
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

          <!-- Button -->
          <button
            @click="handleSearch"
            class="bg-red-600 hover:bg-red-700 text-white font-semibold py-3.5 px-10 rounded-lg transition shadow-md whitespace-nowrap text-base"
          >
            Search Jobs
          </button>
        </div>
      </div>
    </section>

   
<main class="flex-grow py-12 px-5 md:px-8 lg:px-12 bg-gray-100">
  <div class="max-w-7xl mx-auto">
    <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mb-8 text-center md:text-left pl-3">
      Featured Jobs
    </h2>

    <!-- Carousel Container -->
    <div 
      class="relative overflow-hidden"
      @mouseenter="pauseAutoSlide = true"
      @mouseleave="pauseAutoSlide = false"
    >
      <!-- Slider Track -->
      <div 
        class="flex transition-transform duration-700 ease-in-out"
        :style="{ transform: `translateX(-${currentIndex * (100 / visibleCards)}%)` }"
      >
        <div 
          v-for="(job, index) in jobs"
          :key="index"
          class="flex-shrink-0 px-3"
          :class="`w-1/${visibleCards}`"
        >
          <AppJobCard
            :title="job.title"
            :company="job.company || 'Company Name'"
            :location="job.location || 'Phnom Penh'"
            :salary="job.salary || '$400 – $1,200'"
            :image="job.image"
            :bg="job.bg"
          />
        </div>
      </div>

      <!-- Left Arrow -->
      <button 
        @click="prevSlide"
        class="absolute left-0 top-1/2 -translate-y-1/2 bg-white/80 hover:bg-white text-gray-800 p-3 rounded-full shadow-lg z-10 transition opacity-70 hover:opacity-100 disabled:opacity-30"
        :disabled="currentIndex === 0"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
        </svg>
      </button>

      <!-- Right Arrow -->
      <button 
        @click="nextSlide"
        class="absolute right-0 top-1/2 -translate-y-1/2 bg-white/80 hover:bg-white text-gray-800 p-3 rounded-full shadow-lg z-10 transition opacity-70 hover:opacity-100 disabled:opacity-30"
        :disabled="currentIndex >= jobs.length - visibleCards"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>

      <!-- Dots Indicators -->
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
  <section class="w-full bg-gray-200 py-6">
    <div class="max-w-7xl mx-auto px-6">
      
      <!-- Title -->
      <h2 class="text-3xl font-bold text-gray-900 mb-6">
        Top Employers
      </h2>

      <!-- Logo Slider Container -->
      <div class="relative">

        <!-- Logos Wrapper -->
        <div id="logoSlider"
          class="flex items-center gap-8 overflow-x-auto scroll-smooth no-scrollbar px-10">
          
          <!-- Logo Items -->
          <img src="../assets/c1.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c2.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c3.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c4.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c5.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c6.webp" class="h-16 object-contain shrink-0" />
           <img src="../assets/c1.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c2.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c3.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c4.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c5.webp" class="h-16 object-contain shrink-0" />
          <img src="../assets/c6.webp" class="h-16 object-contain shrink-0" />
        </div>

      </div>
    </div>
  </section>

 <!-- Parent container - this creates 2 columns -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-6 p-4">
  
  <!-- Job card 1 -->
  <div class="bg-white rounded-2xl border border-gray-200 shadow-sm p-6 flex flex-col justify-between hover:shadow-md transition">
    <div>
      <!-- Header -->
      <div class="flex justify-between items-center">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center font-semibold">
            {{ logo }}
          </div>
          <span class="text-gray-700 font-medium">{{ company }}</span>
        </div>
        <button class="w-9 h-9 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-100 transition">
          ♡
        </button>
      </div>

      <!-- Title -->
      <h2 class="mt-4 text-lg font-semibold text-gray-900">
        {{ title }} ({{ time }})
      </h2>

      <!-- Salary -->
      <p class="mt-1 text-gray-600">{{ salary }}</p>

      <!-- Details -->
      <div class="grid grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm text-gray-600">
        <div>
          <span class="block text-xs text-gray-400">Office</span>
          {{ office }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Location</span>
          {{ location }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Closing Date</span>
          {{ closingDate }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Employment</span>
          {{ employment }}
        </div>
      </div>
    </div>

    <button class="mt-6 w-full py-3 rounded-full border border-red-500 text-red-500 font-medium hover:bg-red-500 hover:text-white transition">
      View More
    </button>
  </div>

  <!-- Job card 2 - same structure, different data -->
  <div class="bg-white rounded-2xl border border-gray-200 shadow-sm p-6 flex flex-col justify-between hover:shadow-md transition">
    <div>
      <!-- Header -->
      <div class="flex justify-between items-center">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center font-semibold">
            {{ logo }}
          </div>
          <span class="text-gray-700 font-medium">{{ company }}</span>
        </div>
        <button class="w-9 h-9 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-100 transition">
          ♡
        </button>
      </div>

      <!-- Title -->
      <h2 class="mt-4 text-lg font-semibold text-gray-900">
        {{ title }} ({{ time }})
      </h2>

      <!-- Salary -->
      <p class="mt-1 text-gray-600">{{ salary }}</p>

      <!-- Details -->
      <div class="grid grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm text-gray-600">
        <div>
          <span class="block text-xs text-gray-400">Office</span>
          {{ office }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Location</span>
          {{ location }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Closing Date</span>
          {{ closingDate }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Employment</span>
          {{ employment }}
        </div>
      </div>
    </div>

    <button class="mt-6 w-full py-3 rounded-full border border-red-500 text-red-500 font-medium hover:bg-red-500 hover:text-white transition">
      View More
    </button>
  </div>

  <!-- Add more cards here - they will automatically go to next row after 2 items -->

</div>
<!-- Parent container - this creates 2 columns -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-6 p-4">
  
  <!-- Job card 1 -->
  <div class="bg-white rounded-2xl border border-gray-200 shadow-sm p-6 flex flex-col justify-between hover:shadow-md transition">
    <div>
      <!-- Header -->
      <div class="flex justify-between items-center">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center font-semibold">
            {{ logo }}
          </div>
          <span class="text-gray-700 font-medium">{{ company }}</span>
        </div>
        <button class="w-9 h-9 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-100 transition">
          ♡
        </button>
      </div>

      <!-- Title -->
      <h2 class="mt-4 text-lg font-semibold text-gray-900">
        {{ title }} ({{ time }})
      </h2>

      <!-- Salary -->
      <p class="mt-1 text-gray-600">{{ salary }}</p>

      <!-- Details -->
      <div class="grid grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm text-gray-600">
        <div>
          <span class="block text-xs text-gray-400">Office</span>
          {{ office }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Location</span>
          {{ location }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Closing Date</span>
          {{ closingDate }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Employment</span>
          {{ employment }}
        </div>
      </div>
    </div>

    <button class="mt-6 w-full py-3 rounded-full border border-red-500 text-red-500 font-medium hover:bg-red-500 hover:text-white transition">
      View More
    </button>
  </div>

  <!-- Job card 2 - same structure, different data -->
  <div class="bg-white rounded-2xl border border-gray-200 shadow-sm p-6 flex flex-col justify-between hover:shadow-md transition">
    <div>
      <!-- Header -->
      <div class="flex justify-between items-center">
        <div class="flex items-center gap-3">
          <div class="w-10 h-10 rounded-full bg-gray-200 flex items-center justify-center font-semibold">
            {{ logo }}
          </div>
          <span class="text-gray-700 font-medium">{{ company }}</span>
        </div>
        <button class="w-9 h-9 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-100 transition">
          ♡
        </button>
      </div>

      <!-- Title -->
      <h2 class="mt-4 text-lg font-semibold text-gray-900">
        {{ title }} ({{ time }})
      </h2>

      <!-- Salary -->
      <p class="mt-1 text-gray-600">{{ salary }}</p>

      <!-- Details -->
      <div class="grid grid-cols-2 gap-x-6 gap-y-4 mt-5 text-sm text-gray-600">
        <div>
          <span class="block text-xs text-gray-400">Office</span>
          {{ office }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Location</span>
          {{ location }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Closing Date</span>
          {{ closingDate }}
        </div>
        <div>
          <span class="block text-xs text-gray-400">Employment</span>
          {{ employment }}
        </div>
      </div>
    </div>

    <button class="mt-6 w-full py-3 rounded-full border border-red-500 text-red-500 font-medium hover:bg-red-500 hover:text-white transition">
      View More
    </button>
  </div>

  <!-- Add more cards here - they will automatically go to next row after 2 items -->

</div>





<!-- ... AppFooter remains the same ... -->
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
// ... other imports remain ...

// Slider logic
const currentIndex = ref(0)
const pauseAutoSlide = ref(false)

// How many cards visible at once (responsive)
const visibleCards = computed(() => {
  if (window.innerWidth < 640) return 1     // mobile
  if (window.innerWidth < 1024) return 2    // tablet
  return 4                                  // desktop
})

const nextSlide = () => {
  if (currentIndex.value < jobs.value.length - visibleCards.value) {
    currentIndex.value += visibleCards.value
  } else {
    currentIndex.value = 0  // loop back to start
  }
}

const prevSlide = () => {
  if (currentIndex.value > 0) {
    currentIndex.value -= visibleCards.value
  } else {
    currentIndex.value = Math.max(0, jobs.value.length - visibleCards.value)
  }
}

// Auto slide
let interval = null
const startAutoSlide = () => {
  interval = setInterval(() => {
    if (!pauseAutoSlide.value) {
      nextSlide()
    }
  }, 5000)  // change every 5 seconds
}

onMounted(() => {
  startAutoSlide()
  // Recalculate visibleCards on resize
  window.addEventListener('resize', () => {
    currentIndex.value = 0  // reset position on resize for simplicity
  })
})

onUnmounted(() => {
  if (interval) clearInterval(interval)
})

// Expanded jobs array (more featured jobs)
const jobs = ref([
  {
    title: "Senior Graphic Designer",
    company: "Creative Studio KH",
    location: "Phnom Penh",
    salary: "$800 – $1,500",
    image: "https://images.unsplash.com/photo-1556740738-b6a63e27c4df?auto=format&fit=crop&w=800&q=80",
    bg: "bg-red-500"
  },
  {
    title: "Sales Executive",
    company: "Real Estate Cambodia",
    location: "Phnom Penh & Siem Reap",
    salary: "$500 + commission",
    image: "https://images.unsplash.com/photo-1557804506-669a67965ba0?auto=format&fit=crop&w=800&q=80",
    bg: "bg-red-600"
  },
  {
    title: "Cashier / Customer Service",
    company: "Lucky Market",
    location: "Phnom Penh",
    salary: "$350 – $600",
    image: "https://images.unsplash.com/photo-1556740738-b6a63e27c4df?auto=format&fit=crop&w=800&q=80",
    bg: "bg-blue-700"
  },
  {
    title: "Junior Web Developer",
    company: "TechNova Solutions",
    location: "Phnom Penh (Hybrid)",
    salary: "$600 – $1,200",
    image: "https://images.unsplash.com/photo-1557804506-669a67965ba0?auto=format&fit=crop&w=800&q=80",
    bg: "bg-purple-600"
  },
  {
    title: "Marketing Specialist",
    company: "Digital KH Agency",
    location: "Siem Reap",
    salary: "$700 – $1,400",
    image: "https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&w=800&q=80",
    bg: "bg-pink-600"
  },
  {
    title: "Accountant",
    company: "Finance Pro Ltd",
    location: "Phnom Penh",
    salary: "$800 – $1,600",
    image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSxyR1Pzyb44AgoPCOjOUa0Xlplzon-w-chVA&s",
    bg: "bg-green-600"
  },
  {
    title: "Hotel Receptionist",
    company: "Riverside Boutique Hotel",
    location: "Siem Reap",
    salary: "$400 – $800",
    image: "https://images.unsplash.com/photo-1557804506-669a67965ba0?auto=format&fit=crop&w=800&q=80",
    bg: "bg-yellow-600"
  },
  {
    title: "Content Creator",
    company: "Khmer Media Group",
    location: "Phnom Penh (Remote OK)",
    salary: "$500 – $1,000",
    image: "https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&w=800&q=80",
    bg: "bg-indigo-600"
  },
  // You can keep adding more...
])
</script>
