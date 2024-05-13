<template>
  <div class="min-h-screen flex flex-col">
    <LayoutHeader></LayoutHeader>
    <div class="flex-1 container max-w-7xl mx-auto">
      <Nuxt />
    </div>
    <div
      class="
        bg-indigo-50 bg-opacity-50
        border-t border-indigo-50
        px-2
        py-2
        text-center
      "
    >
    </div>
    <LayoutFooter></LayoutFooter>
    <drawer></drawer>
  </div>
</template>