<template>
  <Layout>
    <LatestArticles :articles="$page.articles.edges" />
  </Layout>
</template>

<page-query>


query Parmegianas{
  articles: allArticlePost {
    edges {
      node {
        id
        path
        preview_image
        title
        nota
        justificativa
        preco
      }
    }
  }
}
</page-query>

<script>
import LatestArticles from "../components/LatestArticles";

export default {
  components: {
    LatestArticles,
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
