<script setup lang="ts">
import Buttom from '../components/Buttom.vue';
import SectionHero from '../components/SectionHero.vue';

</script>

<template>
  <AppHeader />
  <div>
  <SectionHero /> 
  <section class="py-16 bg-white px-8">
  ​    <div class="container mx-auto">
    
    
    <Buttom />

   
    <h2 class="text-2xl font-bold text-black mb-8">All Category</h2>

   <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 p-10 max-w-7xl mx-auto">
    
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
    </div>
      

    <div class="flex justify-center mt-10">
      <button class="bg-red-500 hover:bg-red-600 text-white px-8 py-2.5 rounded-full font-medium transition">
        See More Template
      </button>
    </div>
    <div class="flex flex-col md:flex-row items-center justify-center gap-6 p-8 bg-gray-50 min-h-screen font-sans">
    
    <div class="w-full max-w-sm p-8 bg-white border border-gray-200 rounded-3xl shadow-sm h-[500px] flex flex-col justify-between">
      <div>
        <h3 class="text-xl font-bold text-slate-800 mb-4">Pay Per Download</h3>
        <div class="mb-2">
          <span class="text-gray-500">from</span>
          <span class="text-3xl font-bold text-slate-900 ml-2">$9.99</span>
          <span class="text-gray-500 mx-1 text-xl">to</span>
          <span class="text-3xl font-bold text-slate-900">$149.99</span>
        </div>
        <p class="text-xs text-gray-400 font-semibold italic">***VAT Included</p>
        
        <ul class="mt-8 space-y-4 text-sm text-gray-700">
          <li class="flex items-start gap-3">
            <span class="mt-1  w-5 h-5 border border-gray-400 rounded-full flex items-center justify-center">✓</span>
            <span>Pay Per Download — no hiring plan required</span>
          </li>
          <li class="flex items-start gap-3">
            <span class="mt-1  w-5 h-5 border border-gray-400 rounded-full flex items-center justify-center">✓</span>
            <span>KPI Template for 150 USD / Form</span>
          </li>
        </ul>
      </div>
    </div>

    <div class="w-full max-w-sm bg-white border-4 border-[#0c344b] rounded-[20] shadow-2xl scale-105 z-10 overflow-hidden h-[550px] flex flex-col">
      <div class="bg-[#0c344b] h-8 w-full"></div>
      <div class="p-8 flex flex-col justify-between ">
        <div>
          <h3 class="text-lg font-medium text-gray-600 mb-2">Bundle Plan</h3>
          <h2 class="text-6xl font-bold text-slate-900 mb-10">Free</h2>
          
          <ul class="space-y-6 text-sm text-gray-700">
            <li class="flex items-start gap-3">
              <span class="mt-1  w-5 h-5 border-2 border-emerald-500 text-emerald-500 rounded-full flex items-center justify-center text-[10px] font-bold">✓</span>
              <span>Free bundle with annually hiring billing plan</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="mt-1  w-5 h-5 border-2 border-emerald-500 text-emerald-500 rounded-full flex items-center justify-center text-[10px] font-bold">✓</span>
              <span>Download 3 editable forms/month</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="mt-1  w-5 h-5 border-2 border-emerald-500 text-emerald-500 rounded-full flex items-center justify-center text-[10px] font-bold">✓</span>
              <span>Access Free KPI Template</span>
            </li>
          </ul>
        </div>
        
        <button class="w-full bg-[#0c344b] text-white py-4 rounded-xl font-bold hover:bg-slate-800 transition-colors">
          Subscribe Now
        </button>
      </div>
    </div>

    <div class="w-full max-w-sm p-8 bg-white border border-gray-200 rounded-3xl shadow-sm h-[500px] flex flex-col justify-between">
      <div>
        <h3 class="text-xl font-bold text-slate-800 mb-4">Adds - On Plan</h3>
        <div class="mb-2">
          <span class="text-4xl font-bold text-slate-900">$149.99</span>
          <span class="text-gray-500 text-lg">/year</span>
        </div>
        <p class="text-xs text-gray-400 font-semibold italic">***VAT Included</p>
        
        <ul class="mt-8 space-y-4 text-sm text-gray-700">
          <li class="flex items-start gap-3">
            <span class="mt-1  w-5 h-5 border border-gray-400 rounded-full flex items-center justify-center">✓</span>
            <span>Free bundle with annually hiring billing plan</span>
          </li>
          <li class="flex items-start gap-3">
            <span class="mt-1  w-5 h-5 border border-gray-400 rounded-full flex items-center justify-center">✓</span>
            <span>Download 3 editable forms/month</span>
          </li>
          <li class="flex items-start gap-3">
            <span class="mt-1  w-5 h-5 border border-gray-400 rounded-full flex items-center justify-center">✓</span>
            <span>Access Free KPI Template</span>
          </li>
        </ul>
      </div>
      
      <button class="w-full border border-gray-300 py-4 rounded-xl font-medium text-slate-800 hover:bg-gray-50 transition-colors">
        Purchase Now
      </button>
    </div>

  </div>
  </div>
  
</section>
  </div>
  <Appfooter  />
</template>