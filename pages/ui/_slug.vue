<template>
  <article>
    <h1 class="page-header">{{ article.title }}</h1>

    <nuxt-content :document="article" />

    <div class="my-6">
      <prev-next :prev="prev" :next="next" />
    </div>
  </article>
</template>

<script>
import getSiteMeta from "~/utils/getSiteMeta.js";

export default {
  layout: "Page",

  async asyncData({ $content, params }) {
    const article = await $content("ui", params.slug).fetch();

    const [prev, next] = await $content("ui")
      .only(["title", "slug"])
      .sortBy("title", "asc")
      .surround(params.slug)
      .fetch();

    return {
      article,
      prev,
      next,
    };
  },

  computed: {
    meta() {
      const metaData = {
        type: "article",
        title: this.article.title,
        description: this.article.description,
        url: `${process.env.baseUrl}/ui/${this.$route.params.slug}`,
        // mainImage: this.socialImage,
      };
      return getSiteMeta(metaData);
    },
  },

  head() {
    return {
      title: this.article.title,
      meta: [
        ...this.meta,
        {
          property: "article:published_time",
          content: this.article.createdAt,
        },
        {
          property: "article:modified_time",
          content: this.article.updatedAt,
        },
        {
          property: "article:tag",
          content: this.article.tags ? this.article.tags.toString() : "",
        },
      ],
      link: [
        {
          hid: "canonical",
          rel: "canonical",
          href: `${process.env.baseUrl}/ui/${this.$route.params.slug}`,
        },
      ],
    };
  },
};
</script>

<style>
.bg-gradient {
  background: linear-gradient(41deg, #01b9db 45%, #318fff);
}

.bg-gradient:hover {
  background: linear-gradient(41deg, #0face5 45%, #3f67f7);
}
</style>