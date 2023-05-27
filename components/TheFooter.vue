<template>
  <footer>
    <div class="flex flex-col items-center mt-16">
      <div class="flex mb-2 space-x-2 text-sm text-gray-500 dark:text-gray-400">
        <div>Copyright © {{ new Date().getFullYear() }}</div>
        <div>•</div>
        <a href="/"
          >{{ siteMetadata.author }}</a
        >
      </div>
      </div>
  </footer>
</template>

<script>
import siteMetaInfo from "@/data/sitemetainfo";
export default {
  data() {
    return {
      siteMetadata: siteMetaInfo,
    };
  },
};
</script>
