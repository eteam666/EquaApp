<template>
  <div>
    <header class="pt-16 pb-9 sm:pb-16 sm:text-center">
      <h1
        class="mb-4 text-8xl sm:text-4xl tracking-tight text-slate-800 font-extrabold dark:text-slate-200"
      >
        项目
      </h1>

    </header>
    <div class="mx-auto ">
      <blog-item
        v-for="article in articles"
        :key="article.title"
        :title="article.title"
        :description="article.description"
        :date="article.date"
        :slug="article.slug"
        :language="article.Language"
        :version="article.version"
        :image="article.image"
      ></blog-item>
    </div>
  </div>
</template>

<script>
import BlogItem from "@/components/BlogItem.vue";

export default {
  components: {
    BlogItem
  },
  async asyncData({ $content, params }) {
    const articles = await $content("articles")
      .only([
        "title",
        "description",
        "img",
        "slug",
        "tag",
        "author",
        "date",
        "draft",
        "Language",
        "version",
        "image"
      ])
      .sortBy("date", "asc")
      .fetch();

    return {
      articles
    };
  },
  head: {
    title: "所有项目",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        hid: "description",
        name: "description",
        content: "项目集",
      },
    ],
    link: [{ rel: "icon", type: "image/x-icon", href: "/favicon.ico" }],
  },
};
</script>

<style></style>

