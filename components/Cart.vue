<template>
    <div v-for="i in 12" :key="i" class="max-w-[320px] mx-auto bg-white rounded-2xl shadow-xl overflow-hidden border border-gray-100 group cursor-pointer hover:scale-105 transition-transform duration-300">
      <div class="relative h-48 w-full bg-[#003d52] overflow-hidden">
        <div class="absolute inset-0 opacity-40" style="background-image: url('https://www.transparenttextures.com/patterns/carbon-fibre.png');"></div>
        <div class="absolute -left-10 -top-10 w-40 h-40  border-cyan-500/30 rounded-full"></div>
        
        <div class="absolute inset-0 flex items-center justify-center p-6">
          <div class="bg-white/10 backdrop-blur-md border border-white/30 rounded-xl p-4 w-full h-24 flex items-center justify-center text-center shadow-2xl">
            <span class="text-xs font-bold text-white uppercase tracking-wider leading-relaxed">
              SOP - ONBOARDING <br/> & EMPLOYEE ORIENTATION
            </span>
          </div>
        </div>

        <div class="absolute top-4 right-4 bg-amber-400 p-1.5 rounded-lg shadow-lg">
          <svg class="h-4 w-4 text-white" viewBox="0 0 24 24" fill="currentColor">
            <path d="M5 16L3 5L8.5 10L12 4L15.5 10L21 5L19 16H5M19 19C19 19.6 18.6 20 18 20H6C5.4 20 5 19.6 5 19V18H19V19Z" />
          </svg>
        </div>
      </div>

      <div class="p-5 bg-gray-50/50">
        <p class="font-semibold text-slate-800 text-sm leading-6 line-clamp-2">
         SOP - ONBOARDING & EMPLOYEE ORIENTATION
        </p>
      </div>
    </div>
</template>
<script>

</script>