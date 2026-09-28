<template>
  <a
    href="#"
    target="_blank"
    rel="noopener noreferrer"
    class="group flex w-full items-center gap-4 rounded-xl border border-gray-700 bg-gray-800 p-4 shadow-md shadow-gray-900/50 transition-all duration-300 hover:scale-[1.02] hover:border-green-600 hover:shadow-xl hover:shadow-green-500/20"
  >
    <!-- Icon Container -->
    <div
      class="flex h-12 w-12 shrink-0 items-center justify-center rounded-lg bg-gray-700 text-green-400 transition-all duration-300 group-hover:scale-110 group-hover:bg-green-500 group-hover:text-white group-hover:shadow-xl group-hover:shadow-green-500/20"
    >
      <svg
        viewBox="0 0 24 24"
        fill="none"
        stroke=" currentColor"
        class="h-6 w-6 transition-transform duration-300 group-hover:rotate-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M5 21V4h9l.4 2H20v10h-7l-.4-2H7v7zm9.65-7H18V8h-5.25l-.4-2H7v6h7.25z"
        />
      </svg>
    </div>

    <!-- Text Content -->
    <div class="min-w-0 flex-1">
      <h3 class="truncate font-display font-semibold text-white">Link Title</h3>
      <p class="truncate text-sm text-gray-400">Link Description</p>
    </div>

    <!-- Hover Glow Effect -->
    <div
      class="absolute inset-0 rounded-xl bg-linear-to-r from-green-500/0 via-green-500/10 to-green-500/0 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
    />
  </a>
</template>
