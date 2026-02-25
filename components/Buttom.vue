<template>
  <div class="max-w-md mb-8">
      <div class="relative flex items-center">
        <input 
          type="text" 
          placeholder="Search Articles" 
          class="w-full border border-gray-300 rounded-l-lg px-4 py-2 focus:outline-none"
        />
        
        <button class="bg-[#db4444] p-2.5 rounded-r-lg">
          <svg xmlns="" class="h-5 w-5 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
        </button>

      </div>
    </div>

    <div id="category-container" class="flex flex-wrap gap-3 mb-12">
     <a href="/">
      <button class="category-btn active px-6 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
        All Category
      </button>
    </a>

   <a href="http://localhost:3000/sop"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    SOP
  </button></a>

    <a href="http://localhost:3000/form"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    Form
  </button></a>

   <a href="http://localhost:3000/kpiemplate"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    KPI Template
  </button></a>

   <a href="http://localhost:3000/contract"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    Contract
  </button></a>
</div>
</template>