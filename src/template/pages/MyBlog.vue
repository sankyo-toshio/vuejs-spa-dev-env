<template>
  <article>
    <div class="myblog">
      <div v-html="compiledMarkdownText" />
    </div>
  </article>
</template>

<script>
import marked from "marked";
import md from "../assets/markdown.md";

export default {
  name: "MyBlog",
  data() {
    return {
      markdownText: md.source // sourceで Rawデータが取得できます
    };
  },
  computed: {
    compiledMarkdownText: function() {
      return marked(this.markdownText); // computedにする必要あるかどうかは知らん
    }
  }
};
</script>

<style scoped>
</style>