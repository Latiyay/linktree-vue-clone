<script setup>
const projects = [
  {
    title: 'Expense Splitter',
    description: 'A web application for calculating and splitting shared expenses.',
    technologies: ['HTML', 'CSS', 'JavaScript'],
    github: 'https://github.com/Latiyay/expenses-splitter',
  },
  {
    title: 'Expense Splitter – Vue Version',
    description: 'My Expense Splitter rebuilt with Vue.js and reusable components.',
    technologies: ['Vue.js', 'JavaScript', 'CSS'],
    github: 'https://github.com/Latiyay/expense-splitter-vue',
  },
]
</script>

<template>
  <main
    class="min-h-screen bg-linear-to-b from-gray-950 via-gray-900 to-pink-950 px-4 py-12 text-white"
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
          <h2 class="text-2xl font-semibold text-white">{{ project.title }}</h2>
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
            :href="project.github"
            target="_blank"
            rel="noopener noreferrer"
            class="mt-6 inline-block rounded-lg bg-emerald-600 px-5 py-2 font-medium text-white transition hover:bg-emerald-500"
          >
            View on GitHub ↗
          </a>
        </article>
      </div>
    </div>
  </main>
</template>
