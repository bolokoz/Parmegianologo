<template>
  <Layout>
    <div class="container mx-auto w-3/4 py-3">
      <h3 class="font-bold text-5xl">Tabela comparativa</h3>
    </div>

    <div>
      <table>
        <tr>
          <th>Data</th>
          <th>Restaurante</th>
          <th>Nota</th>
          <th>Preço</th>
          <th>Link</th>
        </tr>
        <tr v-for="(prato, i) in $page.articles.edges" :key="i">
          <td>{{ prato.node.date }}</td>
          <td>{{ prato.node.title }}</td>
          <td>{{ prato.node.nota }}</td>
          <td>R$ {{ prato.node.preco }}</td>
          <td>
            <g-link :to="prato.node.path">Ver mais</g-link>
          </td>
        </tr>
      </table>
    </div>
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
        date (format: "DD/MM/YY")
        justificativa
        preco
        cidade
      }
    }
  }
}
</page-query>

<script>
export default {
  data() {
    return {};
  },
  metaInfo: {
    title: "Tabela",
  },
};
</script>

<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>