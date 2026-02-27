<template>
  <div class="min-h-screen bg-gray-50 py-8 px-4 sm:px-6 lg:px-8">
    <div class="max-w-5xl mx-auto">

      <!-- Loading -->
      <div v-if="pending" class="flex justify-center items-center py-20">
        <div class="animate-spin rounded-full h-12 w-12 border-b-2 border-red-500"></div>
      </div>

      <!-- Error -->
      <div v-else-if="error" class="text-center py-20">
        <p class="text-red-500">Failed to load job details.</p>
        <button @click="refresh()" class="mt-4 text-blue-600 hover:underline">
          Retry
        </button>
      </div>

      <!-- Job Content -->
      <template v-else-if="job">

        <!-- Location -->
        <div class="flex items-center justify-center sm:justify-start gap-2 text-sm font-medium text-gray-900">
          <svg
            class="w-4 h-4 text-gray-400"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
            />
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
            />
          </svg>
          {{ job.location }}
        </div>

        <!-- Title -->
        <h1 class="text-3xl font-bold mt-4">
          {{ job.title }}
        </h1>

        <!-- Company -->
        <p class="text-gray-600 mt-2">
          {{ job.company }}
        </p>

        <!-- Salary -->
        <p class="text-red-600 font-semibold mt-2">
          {{ job.salary }}
        </p>

      </template>

    </div>
  </div>
</template>

<script setup>
const route = useRoute()
const id = route.params.id

const API_URL = 'http://localhost:1337'

const { data, pending, error, refresh } = await useFetch(
  `${API_URL}/api/find-jobs/${id}`
)

/* SAFE NORMALIZER (v4 + v5) */
const job = computed(() => {
  if (!data.value?.data) return null

  const item = data.value.data
  const content = item.attributes ? item.attributes : item

  return {
    id: item.id,
    title: content.title || '',
    company: content.company || '',
    location: content.location || '',
    salary: content.salary || '',
    employment: content.employment || '',
  }
})
</script>