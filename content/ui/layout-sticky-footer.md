---
title: Layout Sticky Footer
description: Layout Sticky Footer
alt: Layout Sticky Footer
---

<p class="page-desc">Notice that the footer stick at the bottom eventhough the content is short</p>

<base-snippet :centered_preview="false" custom_preview_class="h-72 p-4">

  <template v-slot:preview>
    <div class="h-full flex flex-col border border-indigo-300 text-xs">
      <header class="p-2 bg-indigo-50 border-b border-indigo-300">Header</header>
      <main class="flex-1 bg-indigo-50 border-b border-indigo-300 p-2">
        <div class="mb-20">Content</div>
      </main>
      <footer class="p-2 bg-indigo-50">Footer</footer>
    </div>
  </template>

  ```html
  <div class="min-h-screen flex flex-col">
    <header class="...">Header</header>
    <main class="flex-1 ..."></main>
    <footer class="...">Footer</footer>
  </div>
  ```

  <template v-slot:source>
    <a class="btn btn-primary btn-lg" href="https://play.tailwindcss.com/hvSifp5tCd">Live Edit</a>
  </template>

</base-snippet>

<related-ui search_key="layout"></related-ui>