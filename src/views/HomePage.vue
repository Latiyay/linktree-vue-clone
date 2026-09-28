<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Latisha Washington',
  slogan: 'Web Developer and Student',
  avatar:
    'https://api.dicebear.com/10.x/micah/svg?clothesVariant=collared&earringsVariant=hoop&earsVariant=attached&eyebrowsVariant=eyelashesUp,up&eyesVariant=eyes,smiling,smilingShadow&facialHairVariant=&glassesVariant=round&hairVariant=full&mouthVariant=laughing,pucker,smile,smirk&backgroundColor=f4b8ef&baseColor=77311d,5f2111&earringColor=f9c9b6,e0ddff,f4d150,ffeba4,fc909f,ffedef,ffffff&eyeShadowColor=e0ddff,ffeba4,ffedef,ffffff&facialHairColor=&hairColor=f9c9b6,000000,ac6651,fc909f,77311d,ffffff&shirtColor=f9c9b6,d2eff3,e0ddff,ffeba4,fc909f,ffedef,6bd9e9,ffffff&seed=de3pl48t',
  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/Latiyay',
      icon: 'code',
      description: 'Check out my web projects!',
    },
    {
      id: 2,
      title: 'Linkedin',
      url: 'https://www.linkedin.com/in/latisha-washington-4b48b171/',
      icon: 'briefcase',
      description: 'Connect with me professionally!',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header -->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-green-400 shadow-lg shadow-green-500/20 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-white">{{ profile.name }}</h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{ profile.slogan }}</p>
    </div>

    <!-- Link List -->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigate to Info -->
    <RouterLink
      to="/info"
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
    >
      About me →
    </RouterLink>
  </main>
</template>
