<template>
  <Layout>
    <!-- <ListaParmegianas :articles="$page.articles.edges" /> -->
    <List>
      <ListItem
        v-for="article in $page.articles.edges"
        :key="article.id"
        :item="article.node"
      />
    </List>
  </Layout>
</template>

<page-query>


query Parmegianas{
  articles: allArticlePost {
    edges {
      node {
        id
        path
        imagens
        title
        nota
        date (format: "DD/MM/YY")
        justificativa
        preco
        parmegianologoscore
        porcao
        cidade
      }
    }
  }
}
</page-query>


<script>
// import ListaParmegianas from "../components/ListaParmegianas";
import List from "../components/List";
import ListItem from "../components/ListItem";

export default {
  components: {
    List,
    ListItem,
  },
  metaInfo: {
    title: "Parmegianólogo",
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
