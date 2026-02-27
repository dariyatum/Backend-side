<template>
  <header class="fixed top-0 left-0 w-full z-50 bg-white/80 backdrop-blur-md shadow-sm">
    <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">

      <!-- Logo -->
      <NuxtLink to="/" class="text-2xl font-bold text-indigo-600 tracking-wide">
        <img src="https://i.ibb.co/5h8vwymK/Chat-GPT-Image-Feb-16-2026-01-32-04-PM-2.png" alt="" class="object-contain w-40 h-20">
      </NuxtLink>

      <!-- Desktop Navigation -->
      <nav class="hidden md:flex items-center gap-8">
        <NuxtLink
      <nav class="hidden md:flex items-center gap-8">
  <div v-for="link in links" :key="link.name" class="relative group">
    <!-- Parent link -->
      <NuxtLink
        v-if="!link.submenu"
        :to="link.path"
        class="relative text-gray-700 font-medium hover:text-red-600 transition duration-300"
        active-class="text-red-600"
      >
        {{ link.name }}
      </NuxtLink>

    <!-- Dropdown parent -->
    <div v-else>
      <span
        class="cursor-pointer relative text-gray-700 font-medium hover:text-red-600 transition duration-300"
      >
        {{ link.name }}
      </span>

      <!-- Dropdown menu -->
      <div
        class="absolute left-0 mt-2 w-52 bg-white shadow-lg rounded-md opacity-0 group-hover:opacity-100 transition-opacity z-50"
      >
        <ul>
          <li
            v-for="sublink in link.submenu"
            :key="sublink.name"
          >
            <NuxtLink
              :to="sublink.path"
              class="block px-4 py-2 hover:bg-gray-100 text-gray-700"
            >
              {{ sublink.name }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
        </NuxtLink>

        <!-- CTA / Auth Section -->
        <div v-if="!user">
          <NuxtLink
            to="/register"
            class="bg-red-600 text-white px-5 py-2 rounded-xl hover:bg-red-700 transition duration-300 shadow-md hover:shadow-lg"
          >
            Get Started
          </NuxtLink>
        </div>

        <div v-else class="flex items-center gap-4">
          <span class="text-gray-700 font-medium">
            Hi, {{ user.name }}
          </span>

          <button
            @click="logout"
            class="text-red-600 font-medium hover:underline"
          >
            Logout
          </button>
        </div>
      </nav>

      <!-- Mobile Menu Button -->
      <button
        @click="isOpen = !isOpen"
        class="md:hidden text-gray-700 focus:outline-none"
      >
        <svg v-if="!isOpen" xmlns="http://www.w3.org/2000/svg" class="h-7 w-7" fill="none"
          viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16" />
        </svg>

        <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-7 w-7" fill="none"
          viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <transition name="fade">
      <div v-if="isOpen" class="md:hidden bg-white shadow-lg px-6 pb-6">
        <NuxtLink
          v-for="link in links"
          :key="link.name"
          :to="link.path"
          class="block py-3 text-gray-700 hover:text-indigo-600 transition"
          @click="isOpen = false"
        >
          {{ link.name }}
        </NuxtLink>

        <div v-if="!user" class="mt-4">
          <NuxtLink
            to="/register"
            class="block bg-red-600 text-white text-center py-2 rounded-lg hover:bg-red-700 transition"
            @click="isOpen = false"
          >
            Get Started
          </NuxtLink>
        </div>

        <div v-else class="mt-4 flex items-center justify-between px-2">
          <span class="text-gray-700 font-medium">Hi, {{ user.name }}</span>
          <button @click="logout" class="text-red-600 font-medium hover:underline">Logout</button>
        </div>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isOpen = ref(false)
const user = ref(null)

const links = [
  { name: 'Home', path: '/' },
  { name: 'Recruit Talent', path: '/recruit-talent' },
  { name: 'Find Jobs', path: '/find-jobs' },
  { name: 'HR Toolkit', path: '/hr-toolkit' },
  { name: 'Products', 
    submenu: [
      { name: 'Hiring Subscription', path: '/hiring-subscription' },
      { name: 'HR Toolkit Subscription', path: '/hrtoolkit-subscription' },
    ]
  },
  { name: 'Why Us?', path: '/why-us' }

]

// Load user from localStorage on mount
onMounted(() => {
  const storedUser = localStorage.getItem('currentUser')
  if (storedUser) user.value = JSON.parse(storedUser)
})

function logout() {
  localStorage.removeItem('currentUser')
  user.value = null
  window.location.href = '/' // redirect to home
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
  