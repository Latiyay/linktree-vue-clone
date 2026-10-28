<script setup>
const projects = [
  //{
  //title: 'Expense Splitter',
  //description: 'A web application for calculating and splitting shared expenses.',
  //technologies: ['HTML', 'CSS', 'JavaScript'],
  //github: 'https://github.com/Latiyay/expenses-splitter',
  //},
  {
    title: 'Expense Splitter – Vue Version',
    status: 'Completed',
    description:
      'A responsive expense-splitting application built with Vue.js, featuring reusable components to help users calculate and divide shared expenses.',
    technologies: ['Vue.js', 'JavaScript', 'CSS'],
    github: 'https://github.com/Latiyay/expense-splitter-vue',
    live: 'https://expense-splitter-vue.latisha-w.workers.dev/',
  },

  {
    title: 'Anime Roulette Machine',
    status: 'In Progress',
    description:
      'An interactive Vue.js application that integrates an anime API to generate randomized recommendations and help users discover new shows.',
    technologies: ['Vue.js', 'Tailwind CSS', 'JavaScript', 'REST API'],
    github: 'https://github.com/Latiyay/anime-roulette-watchlist',
    live: 'https://anime-roulette-machine.latisha-w.workers.dev',
  },
  {
    title: 'Game ConQuest',
    status: 'Coming Soon',
    description:
      'An upcoming gaming-themed web application currently in the design and planning stage. Stay tuned for updates!',
    technologies: ['Figma', 'UI/UX Design', 'Web Development'],
  },
]
</script>

<template>
  <main
    class="flex min-h-screen flex-col items-center bg-linear-to-b from-gray-950 via-gray-900 to-pink-400 px-4 py-12 text-white"
  >
    <div class="mx-auto max-w-2xl">
      <RouterLink
        to="/"
        class="text-sm text-pink-300 hover:text-pink-200"
      >
        ← Back to Home
      </RouterLink>

      <header class="my-10 text-center">
        <h1 class="text-4xl font-bold text-pink-300">My Projects 🩷</h1>
        <p class="mt-3 text-gray-400">A little collection of what I've been building.</p>
      </header>

      <div class="space-y-6">
        <article
          v-for="project in projects"
          :key="project.title"
          class="rounded-2xl border border-emerald-400/30 bg-gray-800/80 p-6 shadow-xl transition hover:-translate-y-1 hover:border-pink-400 hover:shadow-pink-500/20"
        >
          <div class="flex flex-wrap items-center justify-between gap-3">
            <h2 class="text-2xl font-semibold text-white">
              {{ project.title }}
            </h2>

            <span
              class="rounded-full border border-green-400/40 bg-green-900/50 px-3 py-1 text-xs font-semibold text-green-300"
            >
              {{
                project.status === 'Completed' ? '✓' : project.status === 'Coming Soon' ? '✦' : '◷'
              }}
              {{ project.status }}
            </span>
          </div>

          <p class="mt-3 text-gray-300">{{ project.description }}</p>

          <div class="mt-5 flex flex-wrap gap-2">
            <span
              v-for="technology in project.technologies"
              :key="technology"
              class="rounded-full bg-emerald-900/50 px-3 py-1 text-xs text-emerald-300"
            >
              {{ technology }}
            </span>
          </div>

          <a
            v-if="project.github"
            :href="project.github"
            target="_blank"
            rel="noopener noreferrer"
            class="mt-6 inline-block rounded-lg bg-emerald-600 px-5 py-2 font-medium text-white transition hover:bg-emerald-500"
          >
            View on GitHub ↗
          </a>
          <a
            v-if="project.live"
            :href="project.live"
            target="_blank"
            rel="noopener noreferrer"
            class="mt-6 ml-3 inline-block rounded-lg bg-pink-600 px-5 py-2 font-medium text-white transition hover:bg-pink-500"
          >
            View Live Project ↗
          </a>
        </article>
      </div>
      <!-- More Projects -->
      <div
        class="mx-auto mt-10 max-w-3xl rounded-2xl border border-green-500/30 bg-gray-800 p-6 text-center shadow-lg"
      >
        <h2 class="mb-3 text-xl font-bold text-green-400">More Projects Coming Soon!</h2>

        <p class="leading-relaxed text-gray-300">
          I've completed several web development projects and am continuing to build new
          applications as I expand my skills. Check back soon to see what I'm working on next!
        </p>
      </div>
    </div>
  </main>
</template>
