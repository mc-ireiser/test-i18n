<template>
  <div id="app">
    <ArticleCard />
  </div>
</template>

<script>
import ArticleCard from "@/components/articleCard/ArticleCard.vue";

export default {
  name: "App",
  components: {
    ArticleCard,
  },
};
</script>

<style>
#app {
  text-align: left;
  text-justify: auto;
  margin-top: 60px;
}
</style>
