<template>
  <div class="max-w-6xl mx-auto p-8 font-sans text-[#333]">
    <div class="text-center mb-12">
      <h1 class="text-4xl font-bold leading-tight">
        Reach out to us and <br />
        let us know.
      </h1>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
      <form @submit.prevent="" class="space-y-6">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div class="flex flex-col">
            <label class="text-sm font-semibold mb-2">
              Your Name <span class="text-red-500">*</span>
            </label>
            <input 
              " 
              type="text" 
              placeholder="name@company.com" 
              class="border border-gray-300 p-3 rounded-lg focus:ring-1 focus:ring-red-400 outline-none placeholder-gray-400"
              required 
            />
          </div>
          <div class="flex flex-col">
            <label class="text-sm font-semibold mb-2">
              Your Email Address <span class="text-red-500">*</span>
            </label>
            <input 
            
              type="email" 
              placeholder="name@company.com" 
              class="border border-gray-300 p-3 rounded-lg focus:ring-1 focus:ring-red-400 outline-none placeholder-gray-400"
              required 
            />
          </div>
        </div>

        <div class="flex flex-col">
          <label class="text-sm font-semibold mb-2">
            Phone Number <span class="text-red-500">*</span>
          </label>
          <input 
        
            type="text" 
            placeholder="012 111 222" 
            class="border border-gray-300 p-3 rounded-lg focus:ring-1 focus:ring-red-400 outline-none placeholder-gray-400"
            required 
          />
        </div>

        <div class="flex flex-col">
          <label class="text-sm font-semibold mb-2">
            What would you like to discuss? <span class="text-red-500">*</span>
          </label>
          <textarea 
    
            rows="5" 
            placeholder="Write a short description. More details are preferred. Please provide attachment to the responded email inbox."
            class="border border-gray-300 p-3 rounded-lg focus:ring-1 focus:ring-red-400 outline-none placeholder-gray-400"
            required
          ></textarea>
        </div>

        <div class="text-center">
          <p class="text-red-400 text-sm mb-6 italic font-medium">
            Fields marked with an asterisk (*) are required.
          </p>
          <button 
            type="submit" 
            class="bg-[#E25C50] text-white px-12 py-3 rounded-full font-bold hover:bg-red-600 transition duration-300 shadow-sm"
          >
            Submit Notice
          </button>
        </div>
      </form>

      <div class="space-y-8">
        <div class="rounded-2xl overflow-hidden border border-gray-200 h-64 shadow-sm">
          <iframe 
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3909.013908221865!2d104.9354!3d11.5512!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x310951307b897e99%3A0x86819f7a9096773a!2sAquation%20Office%20Park!5e0!3m2!1sen!2skh!4v1700000000000" 
            class="w-full h-full border-0" 
        
            loading="lazy"
          ></iframe>
        </div>

        <div class="space-y-6">
          <section>
            <h3 class="text-[#E25C50] font-bold text-lg mb-2">Address</h3>
            <p class="leading-relaxed text-gray-700">
              Aquation Office Park, #540, Aquation Building, Koh Pich Street, Phum 14, Sangkat Tonle Bassac, Khan Chamkarmorn, Phnom Penh, Cambodia
            </p>
          </section>

          <section>
            <h3 class="text-[#E25C50] font-bold text-lg mb-1">Email</h3>
            <a href="mailto:sale@workingna.com" class="text-blue-600 hover:underline">sale@workingna.com</a>
          </section>

          <section>
            <h3 class="text-[#E25C50] font-bold text-lg mb-1 uppercase tracking-tight">Contact via TELEGRAM</h3>
            <a href="https://t.me/workingnajob" target="_blank" class="text-blue-600 hover:underline">https://t.me/workingnajob</a>
          </section>

          <section>
            <h3 class="text-[#E25C50] font-bold text-lg mb-1">Phone Numbers</h3>
            <div class="space-x-2">
              <span class="font-bold underline text-gray-800">095 777 151</span>
              <span class="text-gray-400">/</span>
              <span class="font-bold underline text-gray-800">093 317 007</span>
            </div>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>