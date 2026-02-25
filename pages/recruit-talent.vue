<template>
<section class="min-h-screen flex flex-col md:flex-row bg-gray-100">

  
  <div class="md:w-1/2 flex flex-col justify-center px-8 lg:px-16 py-12 bg-[#E5E7EB]">
    
    <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-[#0F3D57] mb-10">
      Take the first step toward a smarter talent strategy
    </h1>

    <div class="flex justify-center md:justify-start">
      <img 
        src="../assets/css/img/Artboard 1.webp"
        alt="Recruitment Illustration"
        class="w-64 sm:w-72 lg:w-80 object-contain"
      >
    </div>

  </div>


  
  <div class="md:w-1/2 flex items-center justify-center px-6 py-12">

    <div class="bg-white w-full max-w-md p-8 rounded-2xl shadow-lg">

      <h2 class="text-xl sm:text-2xl font-semibold text-center mb-6">
        People Core
      </h2>

      
      <div class="mb-4">
        <label class="block mb-1 text-sm font-medium">Email*</label>
        <input 
          type="email"
          placeholder="name@company.com"
          class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-red-400"
        >
      </div>

      
      <div class="mb-4">
        <label class="block mb-1 text-sm font-medium">Password*</label>
        <input 
          type="password"
          placeholder="password"
          class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-red-400"
        >
      </div>

     
      <div class="flex justify-between items-center mb-6 text-sm">
        <label class="flex items-center space-x-2">
          <input type="checkbox" class="accent-red-500">
          <span>Remember</span>
        </label>
        <a href="" class="text-red-500 hover:underline">
          <nuxt-link to="/forgive-pressword">Forgot Password?</nuxt-link>
        </a>
      </div>

      
      <button class="w-full py-3 bg-gradient-to-r from-orange-400 to-red-500 text-white rounded-full font-semibold hover:opacity-90 transition">
        <nuxt-link to="#">Login</nuxt-link>
      </button>

      
      <div class="flex items-center my-6">
        <div class="flex-grow h-px bg-gray-300"></div>
        <span class="px-4 text-sm text-gray-500">
          Don’t have an account?
        </span>
        <div class="flex-grow h-px bg-gray-300"></div>
      </div>

      
        <button class="w-full py-2 border border-red-400 text-red-500 rounded-full hover:bg-red-50 transition">
        <nuxt-link to="/create-account">Create New Account</nuxt-link>
      </button>
     

    </div>

  </div>

</section>
</template>
