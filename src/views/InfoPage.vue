<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Latisha Washington',
  avatar:
    'https://api.dicebear.com/10.x/micah/svg?clothesVariant=collared&earringsVariant=hoop&earsVariant=attached&eyebrowsVariant=eyelashesUp,up&eyesVariant=eyes,smiling,smilingShadow&facialHairVariant=&glassesVariant=round&hairVariant=full&mouthVariant=laughing,pucker,smile,smirk&backgroundColor=f4b8ef&baseColor=77311d,5f2111&earringColor=f9c9b6,e0ddff,f4d150,ffeba4,fc909f,ffedef,ffffff&eyeShadowColor=e0ddff,ffeba4,ffedef,ffffff&facialHairColor=&hairColor=f9c9b6,000000,ac6651,fc909f,77311d,ffffff&shirtColor=f9c9b6,d2eff3,e0ddff,ffeba4,fc909f,ffedef,6bd9e9,ffffff&seed=de3pl48t',
  about: `I'm a CIT student passionate about web development and educational technology. I enjoy creating user-friendly digital experiences and finding ways to improve learning through technology.`,
  skills: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'Python', 'SQL', 'Tailwind CSS'],
  email: 'lwashing@stu.southtexascollege.edu',
  location: 'Houston, Tx',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
    >
      ← Back to Links
    </RouterLink>

    <!-- Profile Card -->
    <div
      class="w-full max-w-lg rounded-2xl border border-gray-700 bg-gray-800 p-6 shadow-xl shadow-gray-900/50 sm:p-8"
    >
      <!-- Header -->
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-green-400 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-gray-400">📍 {{ bio.location }}</p>
        </div>
        <!-- About Section -->
        <div class="mb-6">
          <h2 class="mb-3 text-lg font-semibold text-white">About</h2>
          <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
        </div>
        <!-- Skills Section -->
        <div class="mb-6">
          <h2 class="mb-3 text-lg font-semibold text-white">Skills</h2>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="skill in bio.skills"
              :key="skill"
              class="rounded-full bg-green-900/50 px-3 py-1 text-sm text-green-300"
            >
              {{ skill }}
            </span>
          </div>
        </div>
        <!-- Contact -->
        <div>
          <h2 class="mb-3 text-lg font-semibold text-white">Get in Touch</h2>
          <a
            :href="`mailto:${bio.email}`"
            class="group inline-flex items-center gap-2 rounded-xl bg-green-500 px-6 py-3 font-medium text-white shadow-lg shadow-green-500/30 transition-all duration-200 hover:scale-105 hover:bg-green-600 hover:shadow-xl hover:shadow-green-500/40 active:scale-95"
          >
            <svg
              data-slot="icon"
              fill="none"
              stroke-width="1.5"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
              aria-hidden="true"
              class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
              ></path>
            </svg>
            Send Email
          </a>
        </div>
      </div>
    </div>
  </main>
</template>
