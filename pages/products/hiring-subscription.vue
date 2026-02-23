<template>
  
  <div class="bg-white min-h-screen flex items-center justify-center p-6 md:p-20 font-sans">
    <div class="max-w-6xl w-full flex flex-col md:flex-row items-center gap-12">
      
      <div class="flex-1 text-left">
        <h1 class="text-5xl md:text-7xl font-bold text-black mb-6 leading-tight">
          Discover top <br> talents
        </h1>
        <p class="text-lg md:text-xl text-gray-800 leading-relaxed max-w-md">
          Explore and Meet a wide range of our classic and premier users database and identify their personality.
        </p>
      </div>

      <div class="flex-1 relative flex flex-col items-center">
        
        <div class="relative w-full max-w-md flex items-end justify-center">
          
          <div class="absolute left-0 bottom-20 flex flex-col items-center">
            <div class="relative">
              <svg class="w-12 h-12 text-red-500 absolute -top-6 left-1/2 -translate-x-1/2" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 3L1 9l11 6 9-4.91V17h2V9L12 3zM5 13.18v4L12 21l7-3.82v-4L12 17l-7-3.82z" />
              </svg>
              <div class="w-24 h-32 border-2 border-gray-300 rounded-lg p-3 pt-8 flex flex-col gap-2 bg-white">
                <div class="h-1 w-full bg-gray-200"></div>
                <div class="h-1 w-full bg-gray-200"></div>
                <div class="h-1 w-full bg-gray-200"></div>
                <div class="h-1 w-full bg-gray-200"></div>
              </div>
            </div>
          </div>

          <div class="z-10 w-64 md:w-80 h-[400px] flex items-end">
            <img src="https://cdni.iconscout.com/illustration/premium/thumb/female-recruiter-searching-for-candidate-4487012-3723223.png" 
                 alt="Character" class="w-full object-contain">
          </div>

          <div class="absolute right-0 top-1/4 flex flex-col gap-8">
            <div class="absolute -left-20 top-0 flex gap-1">
               <span class="w-2 h-2 bg-red-400 rounded-full"></span>
               <span class="w-2 h-2 bg-red-400 rounded-full"></span>
               <span class="w-2 h-2 bg-red-400 rounded-full"></span>
            </div>

            <div class="flex items-center gap-2">
              <span class="text-2xl opacity-80"><i class="fa-solid fa-user"></i></span>
              <span class="text-red-500 text-sm">*</span>
            </div>
            <div class="flex items-center gap-2">
              <span class="text-2xl opacity-80"><i class="fa-solid fa-user"></i></span>
              <span class="text-red-500 text-sm">**</span>
            </div>
            <div class="flex items-center gap-2">
              <span class="text-2xl opacity-80"><i class="fa-solid fa-user"></i></span>
              <span class="text-red-500 text-sm">**</span>
            </div>
          </div>

        </div>

        <div class="w-full  bg-slate-900  rounded-full"></div>
      </div>

    </div>
  </div>
    
<section class="bg-[#F8F9FA] py-10 px-4 font-sans text-[#333]">
  <div class="max-w-7xl mx-auto">

    
    <div class="text-center mb-8 md:mb-10">
      <h2 class="text-2xl md:text-4xl font-bold mb-3">
        Multiple packages to choose from.
      </h2>
      <p class="text-gray-600 text-sm md:text-base">
        Pick the most suitable package that fits best for you.
      </p>
    </div>
    
    <div id="category-container" class="flex flex-wrap justify-center gap-3 mb-12">
     
     <div class="category-btn active px-6 py-1.5 rounded-full text-sm font-bold hover:bg-red-500 hover:text-white">
  BILLING CYCLE:

</div>


   <a href="http://localhost:3000/our2"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    Monthly
  </button></a>

    <a href="http://localhost:3000/quarterly"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
      Quarterly
  </button></a>

   <a href="http://localhost:3000/semiannual"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
   Semi Annual
  </button></a>

   <a href="http://localhost:3000/annually"><button class="category-btn px-8 py-1.5 rounded-full text-sm font-bold border border-black hover:bg-red-500 hover:text-white hover:border-red-500">
    Annually
  </button></a>
</div>

    <div class="overflow-x-auto">
      <table class="w-full border-collapse bg-white min-w-[1100px] table-fixed">
        <thead>
          <tr class="text-center">
            <th class="p-4 border border-gray-200 w-[200px]">
              <div class="flex flex-col items-center">
                <img src="https://workingna.com/dist/img/logo-workingna.png" alt="Workingna" class="w-32 mb-2">
                <p class="text-[8px] text-gray-400 uppercase italic">Hire Better and Faster with Data</p>
              </div>
            </th>
            
            <th class="p-4 border border-gray-200 align-top">
              <div class="bg-[#E14D43] text-white py-1 text-[11px] font-bold rounded-full mb-4 mx-4 uppercase">Freemium</div>
              <div class="text-3xl font-bold mb-1">Free</div>
              <p class="text-[10px] text-gray-500 mb-4 italic lowercase">Try it now!</p>
              <button class="border border-red-400 text-red-500 px-4 py-1 rounded-full text-[10px] font-bold hover:bg-red-50">Start Freemium</button>
            </th>

            <th class="p-4 border border-gray-200 align-top bg-[#FFFDF5]">
              <div class="bg-[#E8C547] text-white py-1 text-[11px] font-bold rounded-full mb-2 mx-4 uppercase shadow-sm">AI Hire+</div>
              <div class="text-[10px] text-gray-400 line-through">$299.97 <span class="text-[#8CC63F] font-bold">(15% off)</span></div>
              <div class="text-3xl font-bold text-[#333] mb-1">$254.97</div>
              <p class="text-[9px] text-[#8CC63F] font-bold mb-4">Save up to 45.00$ <span class="block text-gray-400 font-normal">/quarterly</span></p>
              <button class="bg-[#E8C547] text-white px-4 py-1 rounded-full text-[10px] font-bold shadow-md">Start AI Hire+</button>
            </th>

            <th class="p-4 border border-gray-200 align-top bg-[#FFFCF0]">
              <div class=" from-[#D4AF37] to-[#B8860B] text-white py-1 text-[11px] font-bold rounded-full mb-2 mx-4 uppercase shadow-sm">Signature 👑</div>
              <div class="text-[10px] text-gray-400 line-through">$464.97 <span class="text-[#8CC63F] font-bold">(15% off)</span></div>
              <div class="text-3xl font-bold text-[#333] mb-1">$395.22</div>
              <p class="text-[9px] text-[#8CC63F] font-bold mb-4">Save up to 69.75$ <span class="block text-gray-400 font-normal">/quarterly</span></p>
              <button class="bg-[#D4AF37] text-white px-4 py-1 rounded-full text-[10px] font-bold shadow-md">Start Signature</button>
            </th>

            <th class="p-4 border border-gray-200 align-top">
              <div class="bg-[#B32017] text-white py-1 text-[11px] font-bold rounded-full mb-2 mx-4 uppercase">Signature+</div>
              <div class="text-[10px] text-gray-400 line-through">$899.97 <span class="text-[#8CC63F] font-bold">(5% off)</span></div>
              <div class="text-3xl font-bold text-[#333] mb-1">$854.97</div>
              <p class="text-[9px] text-[#8CC63F] font-bold mb-4">Save up to 45.00$ <span class="block text-gray-400 font-normal">/quarterly</span></p>
              <button class="bg-[#B32017] text-white px-4 py-1 rounded-full text-[10px] font-bold">Start Signature+</button>
            </th>
          </tr>
        </thead>

        <tbody>
          <tr class="bg-[#E14D43] text-white font-bold text-[11px]">
            <td class="p-2 border border-gray-300 pl-4 uppercase">Job Visibility & Branding</td>
            <td class="border border-gray-300"></td><td class="border border-gray-300"></td><td class="border border-gray-300"></td><td class="border border-gray-300"></td>
          </tr>
          <tr class="text-sm">
            <td class="p-2 border border-gray-200 pl-4 text-gray-600 font-bold text-[11px]">Job Listing (App & Web)</td>
            <td class="border border-gray-200 text-center text-[#8CC63F]">✔</td>
            <td class="border border-gray-200 text-center text-[#8CC63F]">✔</td>
            <td class="border border-gray-200 text-center text-[#D4AF37] bg-[#FFFCF0]">✔</td>
            <td class="border border-gray-200 text-center text-[#8CC63F]">✔</td>
          </tr>
          <tr>
            <td class="p-2 border border-gray-200 pl-4 text-gray-600 font-bold text-[11px]">Social Media</td>
            <td class="border border-gray-200 text-center text-white bg-[#E14D43] opacity-80">✖</td>
            <td class="border border-gray-200 text-center text-[#8CC63F]">✔</td>
            <td class="border border-gray-200 text-center text-[#D4AF37] bg-[#FFFCF0]">✔</td>
            <td class="border border-gray-200 text-center text-[#8CC63F]">✔</td>
          </tr>

          <tr class="bg-[#E14D43] text-white font-bold text-[11px]">
            <td class="p-2 border border-gray-300 pl-4 uppercase">AI Hire+ Tool</td>
            <td class="border border-gray-300"></td><td class="border border-gray-300"></td><td class="border border-gray-300"></td><td class="border border-gray-300"></td>
          </tr>
          <tr>
            <td class="p-2 border border-gray-200 pl-4 text-gray-600 font-bold text-[11px]">AI-Powered CV Search</td>
            <td class="border border-gray-200 text-center text-white bg-[#E14D43] text-[9px] font-bold">55/CV Download</td>
            <td class="border border-gray-200 text-center text-[#8CC63F] text-[10px] font-bold">90 CVs</td>
            <td class="border border-gray-200 text-center text-[#D4AF37] text-[10px] font-bold bg-[#FFFCF0]">90 CVs</td>
            <td class="border border-gray-200 text-center text-white bg-[#E14D43] text-[10px] font-bold">150 CVs</td>
          </tr>

          <tr class="border-t-4 border-gray-300">
            <td class="p-4 border border-gray-300 bg-[#B32017] text-white font-black text-center text-[10px] uppercase">Hiring Fee</td>
            <td class="p-4 border border-gray-200 text-center">
              <div class="text-[#E14D43] text-2xl font-black italic">$1.49</div>
              <div class="text-[9px] font-bold text-gray-600">Per Application</div>
              <div class="text-[8px] text-gray-400 italic">*** VAT included</div>
            </td>
            <td class="p-4 border border-gray-200 text-center">
              <div class="text-[#E14D43] text-2xl font-black italic uppercase">Free</div>
              <div class="text-[9px] font-bold text-gray-600 uppercase">Unlimited Candidate</div>
            </td>
            <td class="p-4 border border-gray-200 text-center bg-[#FFFCF0]">
              <div class="text-[#E14D43] text-2xl font-black italic uppercase">Free</div>
              <div class="text-[9px] font-bold text-gray-600 uppercase">Unlimited Candidate</div>
            </td>
            <td class="p-4 border border-gray-200 text-center">
              <div class="text-[#E14D43] text-2xl font-black italic uppercase">Free</div>
              <div class="text-[9px] font-bold text-gray-600 uppercase">Unlimited Candidate</div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</section>
 <div class="bg-white py-16 px-4 font-sans">
    <div class="max-w-6xl mx-auto mb-12">
      <h2 class="text-3xl font-bold text-gray-900 mb-2">
        Take the first step toward a smarter talent strategy
      </h2>
      <p class="text-gray-600 text-lg">
        Simply way to make you stress-free from the hiring process
      </p>
    </div>

    <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
      
      <div class="border border-gray-100 rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow text-center">
        <div class="flex justify-center mb-6">
          <div class="w-16 h-16 bg-red-50 rounded-lg flex items-center justify-center">
            <span class="text-red-500 text-3xl">🖥️</span>
          </div>
        </div>
        <h3 class="text-red-500 font-bold mb-4">Publish your Job Vacancy</h3>
        <p class="text-gray-600 leading-relaxed">
          Quickly create your employer account get unlimited jobs posting to promote your job opportunity to the right target audience through our target announcement.
        </p>
      </div>

      <div class="border border-gray-100 rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow text-center">
        <div class="flex justify-center mb-6">
          <div class="w-16 h-16 bg-red-50 rounded-lg flex items-center justify-center">
            <span class="text-red-500 text-3xl">👤</span>
          </div>
        </div>
        <h3 class="text-red-500 font-bold mb-4">Automated Shortlisting Process</h3>
        <p class="text-gray-600 leading-relaxed">
          Automated Shortlisting Process - To reduce the workload on reviewing and shortlisting job applicants, you can shortlist and appoint candidates for an interview with just one finger's tip only.
        </p>
      </div>

      <div class="border border-gray-100 rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow text-center">
        <div class="flex justify-center mb-6">
          <div class="w-16 h-16 bg-red-50 rounded-lg flex items-center justify-center">
            <span class="text-red-500 text-3xl">📈</span>
          </div>
        </div>
        <h3 class="text-red-500 font-bold mb-4">Data Analytic for Assessment Tool</h3>
        <p class="text-gray-600 leading-relaxed">
          Inclusively offering career matching test for shortlisted job applicants to access into their personality style, motivated skill vs burning out skills, and career value to ensure they're truly matched to your requirement.
        </p>
      </div>

    </div>
  </div>
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