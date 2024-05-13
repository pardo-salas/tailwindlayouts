<template>
  <header class="border-b shadow-sm">
    <div class="max-w-7xl mx-auto flex items-center justify-between px-4 py-4">
      <NuxtLink class="font-bold flex-none" to="/">
        <img
          src="/layout-logo.png"
          class="h-[40px]"
          alt="Layouts Logo"
        />
      </NuxtLink>

      <div class="w-full mx-4 sm:mx-8">
        <AppSearchInput />
      </div>

      <button
        class="inline-flex items-center sm:hidden"
        type="button"
        @click="toggleDrawer()"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </button>

      <div class="hidden sm:block ">
        <ul class="flex space-x-6">
          <li>
            <a
              href="https://github.com/pardo-salas/tailwindlayout"
              target="_blank"
            >
              <img
                src="/github-logo.png"
                class="w-[29px] opacity-60 hover:opacity-80"
                alt="GitHub Logo"
              />
            </a>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  methods: {
    toggleDrawer() {
      $nuxt.$emit("toggleDrawer");
    },
  },
};
</script>