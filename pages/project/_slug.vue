<template>
<div class="root">
    <div class="px-5 py-10 md:px-10" >
    <div class="flex flex-col items-start justify-center h-full px-8 py-20 space-y-2 text-white dark:text-gray-300 bg-gray-800/70 rounded" :style="{ 'background-image': 'url(' + article.image + ')' }">
    <div
      class="flex flex-col items-center space-y-2 text-center text-white cursor-default dark:text-gray-300 postPage-container md:items-start"
    >
      <p class="text-5xl">{{ article.title }}</p>

    </div>
    <div
      class="pt-2 mt-4 text-white  md:border-t dark:text-gray-300"
    >
      <div class="grid grid-cols-3 gap-5 cursor-default md:grid-cols-4">
        <div class="flex flex-col items-center md:items-start">
          <div class="flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
              class="h-4 mr-1"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"
              ></path></svg>程式语言
          </div>
          <p class="text-lg">{{ article.Language }}</p>
        </div>
        <div class="flex flex-col items-center md:items-start">
          <div class="flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
              class="h-4 mr-1"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
              ></path>
            </svg>
            <p>最新版本</p>
          </div>
          <p class="text-lg">{{ article.version }}</p>
        </div>
        <div class="flex flex-col items-center md:items-start">
          <div class="flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
              class="h-4 mr-1"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
              ></path>
            </svg>
            <p>更新时间</p>
          </div>
          <p class="text-lg">{{ formatDate(article.date) }}</p>
        </div>
      </div>
    </div>
  </div>
<div class="px-4 mx-auto sm:px-6 xl:max-w-5xl xl:px-0 mt-10">
  <nuxt-content class="prose min-w-full p-10 mx-auto" :document="article" />
</div>
<div class="flex flex-col items-center justify-between p-5 my-10 shadow-inner sm:flex-row sm:flex-wrap sm:px-24 sm:py-10 rounded-xl bg-slate-100 dark:bg-slate-800">
  <a :href="article.DLCN"  >
  <div class="select-none transition-all transform flex items-center self-center text-white dark:text-gray-200 cursor-pointer no-underline w-48 h-12 justify-center rounded-md shadow-md pointer-events-none bg-red-600 mb-4 sm:mr-4">
    <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 mr-2" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg">
      <polyline points="8 17 12 21 16 17"></polyline>
      <line x1="12" y1="12" x2="12" y2="21"></line>
      <path d="M20.88 18.09A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.29"></path>
    </svg>
    <span class="no-underline text-lg">国内下载</span>
    </div>
  </a>
  <a :href="article.DLHW" >
      <div class="select-none transition-all transform flex items-center self-center text-white dark:text-gray-200 cursor-pointer no-underline w-48 h-12 justify-center rounded-md shadow-md pointer-events-none bg-blue-600 mb-4 sm:mr-4">

    <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 mr-2" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg">
      <polyline points="8 17 12 21 16 17"></polyline>
      <line x1="12" y1="12" x2="12" y2="21"></line>
      <path d="M20.88 18.09A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.29"></path>
    </svg>
    <span class="no-underline text-lg">海外下载</span>
    </div>
  </a>
  <a :href="article.Doc" >
      <div class="select-none transition-all transform flex items-center self-center text-white dark:text-gray-200 cursor-pointer no-underline w-48 h-12 justify-center rounded-md shadow-md pointer-events-none bg-blue-600 mb-4 sm:mr-4">

    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
      <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25m2.25 0H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z" />
    </svg>
    <span class="no-underline text-lg">文档</span>
    </div>
  </a>
</div>

</div>
</div>
</template>
<script>
import Prism from "~/plugins/prism";
import siteMetaInfo from "@/data/sitemetainfo";
export default {
  data() {
    return {
      title: 0,
      siteMetadata: siteMetaInfo,
    };
  },
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug).fetch();
    return {
      article: article,
    };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("zh", options);
    },
  },
  mounted() {
    Prism.highlightAll();
  },
  head() {
    //console.log(this.article.title);
    return {
      title: this.article.title,
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.article.description,
        },
      ],
    };
  },
};
</script>
<style>
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content p {
  margin-bottom: 20px;
}
</style>
