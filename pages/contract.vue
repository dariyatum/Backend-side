<script setup lang="ts">
import AppHeader from '../components/AppHeader.vue';
import SectionHero from '../components/SectionHero.vue';

</script>

<template>
 <AppHeader /> 
  <SectionHero />
    <div class="ml-[100px] mt-[60px]">
  <Buttom />
  </div>
  <div class="bg-gray-50 min-h-screen p-10 font-sans">
    
    <div class="max-w-7xl mx-auto">
      <h2 class="text-2xl font-bold text-slate-900 mb-6">Contract</h2>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        
        <div v-for="i in 4" :key="i" class="bg-white rounded-2xl shadow-sm overflow-hidden border border-gray-100 group cursor-pointer hover:shadow-xl transition-all duration-300">
          
          <div class="relative h-44 w-full bg-[#003d52] flex items-center justify-center p-4">
            <div class="absolute inset-0 opacity-30" 
                 style="background-image: url('https://www.transparenttextures.com/patterns/carbon-fibre.png');">
            </div>
            <div class="absolute inset-0 overflow-hidden">
              <div class="absolute -left-10 -top-10 w-48 h-48 border border-cyan-500/20 rounded-full"></div>
              <div class="absolute right-0 bottom-0 w-32 h-32 border border-cyan-400/10 rounded-full"></div>
            </div>

            <div class="relative z-10 w-full h-24 bg-white/10 backdrop-blur-md border border-white/20 rounded-xl flex items-center justify-center px-4 text-center shadow-lg">
              <span class="text-[11px] md:text-xs font-bold text-white uppercase tracking-wide leading-relaxed">
               Employment Contract - Fixed Duration Contract
              </span>
            </div>

            <div class="absolute top-3 right-3 bg-amber-400 p-1 rounded-md shadow-md">
              <svg class="h-3.5 w-3.5 text-white" viewBox="0 0 24 24" fill="currentColor">
                <path d="M5 16L3 5L8.5 10L12 4L15.5 10L21 5L19 16H5M19 19C19 19.6 18.6 20 18 20H6C5.4 20 5 19.6 5 19V18H19V19Z" />
              </svg>
            </div>
          </div>

          <div class="p-4 bg-white">
            <p class="font-medium text-slate-700 text-[13px] leading-relaxed line-clamp-2">
              Employment Contract - Fixed Duration Contract
            </p>
          </div>
        </div> </div> </div> </div>
        <section class="max-w-7xl mx-auto px-4 py-20">
      <div class="text-center mb-16">
        <h2 class="text-3xl font-bold text-slate-800 mb-2">Pricing Plans</h2>
        <p class="text-gray-500">Choose the best plan for your business needs</p>
      </div>

      <div class="flex flex-col lg:flex-row items-center justify-center gap-8">
        
        <div class="w-full max-w-sm p-8 bg-white border border-gray-200 rounded-3xl shadow-sm h-[520px] flex flex-col justify-between hover:border-blue-200 transition-colors">
          <div>
            <h3 class="text-xl font-bold text-slate-800 mb-4">Pay Per Download</h3>
            <div class="flex items-baseline gap-2 mb-2">
              <span class="text-gray-500 text-sm">from</span>
              <span class="text-3xl font-bold text-slate-900">$9.99</span>
              <span class="text-gray-500">to</span>
              <span class="text-3xl font-bold text-slate-900">$149.99</span>
            </div>
            <p class="text-[10px] text-gray-400 font-semibold italic">***VAT Included</p>
            
            <ul class="mt-10 space-y-4 text-sm text-gray-600">
              <li class="flex items-start gap-3">
                <span class="mt-0. w-5 h-5 border border-gray-300 rounded-full flex items-center justify-center text-xs">✓</span>
                <span>Pay Per Download — no hiring plan required</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="mt-0.5  w-5 h-5 border border-gray-300 rounded-full flex items-center justify-center text-xs">✓</span>
                <span>KPI Template for 150 USD / Form</span>
              </li>
            </ul>
          </div>
          <button class="w-full border border-gray-300 py-4 rounded-xl font-semibold text-slate-700 hover:bg-gray-50 transition-colors mt-6">
            Get Started
          </button>
        </div>

        <div class="w-full max-w-sm bg-white border-4 border-[#0c344b] rounded-[40px] shadow-2xl lg:scale-110 z-10 overflow-hidden h-[580px] flex flex-col relative">
          <div class="bg-[#0c344b] py-3 text-center">
             <span class="text-white text-xs font-bold tracking-widest uppercase">Most Popular</span>
          </div>
          <div class="p-8 flex flex-col justify-between ">
            <div>
              <h3 class="text-lg font-medium text-gray-500 mb-2">Bundle Plan</h3>
              <h2 class="text-6xl font-bold text-slate-900 mb-10">Free</h2>
              
              <ul class="space-y-6 text-sm text-gray-700">
                <li v-for="text in ['Free bundle with annually hiring billing plan', 'Download 3 editable forms/month', 'Access Free KPI Template']" :key="text" class="flex items-start gap-3">
                  <span class="mt-1 w-5 h-5 border-2 border-emerald-500 text-emerald-500 rounded-full flex items-center justify-center text-[10px] font-extrabold">✓</span>
                  <span>{{ text }}</span>
                </li>
              </ul>
            </div>
            <button class="w-full bg-[#0c344b] text-white py-4 rounded-2xl font-bold hover:bg-slate-800 transition-all shadow-lg active:scale-95">
              Subscribe Now
            </button>
          </div>
        </div>

        <div class="w-full max-w-sm p-8 bg-white border border-gray-200 rounded-3xl shadow-sm h-[520px] flex flex-col justify-between hover:border-blue-200 transition-colors">
          <div>
            <h3 class="text-xl font-bold text-slate-800 mb-4">Adds - On Plan</h3>
            <div class="flex items-baseline gap-1 mb-2">
              <span class="text-4xl font-bold text-slate-900">$149.99</span>
              <span class="text-gray-500 text-lg">/year</span>
            </div>
            <p class="text-[10px] text-gray-400 font-semibold italic">***VAT Included</p>
            
            <ul class="mt-10 space-y-4 text-sm text-gray-600">
              <li v-for="text in ['Free bundle with annually hiring billing plan', 'Download 3 editable forms/month', 'Access Free KPI Template']" :key="text" class="flex items-start gap-3">
                <span class="mt-0.5  w-5 h-5 border border-gray-300 rounded-full flex items-center justify-center text-xs">✓</span>
                <span>{{ text }}</span>
              </li>
            </ul>
          </div>
          <button class="w-full border border-gray-300 py-4 rounded-xl font-semibold text-slate-700 hover:bg-gray-50 transition-colors mt-6">
            Purchase Now
          </button>
        </div>

      </div>
    </section>
</template>