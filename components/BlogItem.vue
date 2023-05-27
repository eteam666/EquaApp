<template>
  <div>
    <div class="px-5 py-10 md:px-10" >
      <div class="transform hover:scale-105 rounded-card overflow-hidden mx-0" :style="{ 'background-image': 'url(' + postimage + ')' }">
        <a :href="'/project/' + postSlug">
          <div
            class="flex flex-col items-start justify-center h-full px-8 py-20 space-y-2 text-white dark:text-gray-300 bg-gray-800/70 rounded"
          >
            <div class="w-full pb-3 mb-3 border-b cursor-pointer">
              <h2 class="py-1 text-2xl font-semibold md:text-4xl">{{ postTitle }}</h2>
              <span class="text-sm text-gray-300 md:text-base">{{ postDescription }}</span>
            </div>
            <div class="flex items-center w-full mt-4 md:w-auto">
              <div class="grid w-full grid-cols-2 gap-5 text-white cursor-default md:grid-cols-4 dark:text-gray-300">
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
                      ></path>
                    </svg>
                    程序语言
                  </div>
                  <p class="text-sm">{{ postLanguage }}</p>
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
                  <p class="text-sm">{{ postVersion }}</p>
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
                  <p class="text-sm">{{ formatDate(postDate) }}</p>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
    </div>
    <br />
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    },
    slug: {
      type: String,
      required: true
    },
    language: {
      type: String,
      required: true
    },
    version: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
  },
  data() {
    return {
      postTitle: this.title,
      postDescription: this.description,
      postSlug: this.slug,
      postDate: this.date,
      postLanguage: this.language,
      postVersion: this.version,
      postimage: this.image
    };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("zh", options);
    }
  }
};
</script>

<style></style>

