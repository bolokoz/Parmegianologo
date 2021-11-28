<template>
  <Layout>
    <div class="sm:w-full md:w-3/4 m-auto">
      <div class="bg-white shadow-md p-1 rounded">
        <div class="my-6">
          <CarouselP :images="$page.post.imagens" />
        </div>
        <div class="text-4xl font-bold">
          <span v-text="$page.post.title" class="Article-title"></span>
          <span> - </span>
          <span v-text="$page.post.cidade" class="font-light"></span>
        </div>

        <div class="flex flex-wrap w-full">
          <div class="flex-block">
            <span class="font-semibold">Preço: R$</span>
            <span class="font-semibold mr-5" v-text="$page.post.preco" />
          </div>
          <div class="flex-block">
            <span class="font-semibold">Serve: </span>
            <span class="font-semibold mr-5" v-text="$page.post.porcao" />
          </div>
          <div class="flex-block">
            <span class="font-semibold">Data:</span>
            <span class="font-light ml-2 mr-5" v-text="$page.post.date" />
          </div>
        </div>
        <div class="flex flex-wrap w-full">
          <div class="flex-block">
            <span class="font-semibold">Nota sentimental: </span>
            <span
              class="font-semibold mr-5"
              v-text="$page.post.parmegianologoscore"
            />
            <span class="font-semibold"> </span>
          </div>
          <div class="flex-block">
            <span class="font-semibold">Nota técnica: </span>
            <span class="font-semibold" v-text="rogerScore" />
            <span class="font-semibold"> / 600</span>
          </div>
        </div>

        <div class="pt-5">
          <strong>Introdução:</strong><br />
          <div>
            <p>
              {{ $page.post.introducao }}
            </p>
          </div>
        </div>

        <div>
          <div class="pt-5">
            <span class="font-bold"
              >Carne: {{ $page.post.rogerscore.carne }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.carne_text }}
              </p>
            </div>
            <span class="font-bold"
              >Crosta: {{ $page.post.rogerscore.crosta }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.crosta_text }}
              </p>
            </div>
            <span class="font-bold"
              >Molho / queijo: {{ $page.post.rogerscore.molho }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.molho_text }}
              </p>
            </div>

            <span class="font-bold"
              >Acompanhamentos =>
              {{ $page.post.rogerscore.acompanhamentos_nomes }}:
              {{ $page.post.rogerscore.acompanhamentos }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.acompanhamentos_text }}
              </p>
            </div>
            <span class="font-bold"
              >Montagem: {{ $page.post.rogerscore.montagem }} / 50</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.montagem_text }}
              </p>
            </div>
            <span class="font-bold"
              >Tempo de preparo e restaurante:
              {{ $page.post.rogerscore.tempo }} / 50</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.tempo_text }}
              </p>
            </div>
            <span class="font-bold"
              >Custo benefício: {{ $page.post.rogerscore.custobeneficio }} /
              50</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.custobeneficio_text }}
              </p>
            </div>
            <span class="font-bold"
              >Inovações extras: {{ $page.post.rogerscore.inovacoes }} /
              50</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.inovacoes_text }}
              </p>
            </div>

            <strong
              >Roger Score: {{ $page.post.rogerscore.carne }} +
              {{ $page.post.rogerscore.molho }} +
              {{ $page.post.rogerscore.crosta }} +
              {{ $page.post.rogerscore.custobeneficio }} +
              {{ $page.post.rogerscore.tempo }} +
              {{ $page.post.rogerscore.acompanhamentos }} +
              {{ $page.post.rogerscore.montagem }} +
              {{ $page.post.rogerscore.inovacoes }} = {{ rogerScore }} /
              600</strong
            ><br />

            <div class="pt-5">
              <strong>Parmegianólogo score: </strong><br />
              <div>
                <div class="flex-block">
                  <link
                    rel="stylesheet"
                    href="https://use.fontawesome.com/releases/v5.11.2/css/all.css"
                  />
                  <div>
                    <ul class="flex justify-center">
                      <li v-for="(n, index) in 3" :key="index">
                        <i
                          :class="[
                            index < +$page.post.parmegianologoscore[0]
                              ? 'fa'
                              : 'far',
                          ]"
                          class="fa-star fa-sm text-yellow-500 mr-1"
                        >
                        </i>
                      </li>
                      {{
                        $page.post.parmegianologoscore
                      }}
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="pt-5">
            <strong>Justificativa da nota:</strong><br />
            <div>
              <p>
                {{ $page.post.justificativa }}
              </p>
            </div>
            <div class="pt-5">
              <strong>Recomendações ao Chef:</strong><br />
              <div>
                <p>
                  {{ $page.post.recomendacao }}
                </p>
              </div>
            </div>
          </div>

          --------
          <div>
            <span class="font-italics">
              Para saber mais sobre a metodologia e tabela comparativa
              <a href="https://parmegianologo.netlify.app">
                acesse o site parmegianologo.netlify.app</a
              >
            </span>
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>


query ArticlePost ($path: String!) {
  post: articlePost (path: $path) {
    preview_image
    path
    title
    imagens
    parmegianologoscore
    introducao
    cidade
    date(format: "DD/MM/YY")
    porcao
    preco
    recomendacao
    rogerscore {
      carne
      molho
      queijo
      crosta
      acompanhamento1
      acompanhamento2
      nome_acompanhamento1
      nome_acompanhamento2
      tempo
      custobeneficio
      custobeneficio_text
      montagem
      montagem_text
      carne_text
      molho_text
      queijo_text
      crosta_text
      acompanhamentos
      acompanhamentos_text
      acompanhamentos_nomes
      acompanhamento1_text
      acompanhamento2_text
      tempo_text
      inovacoes
      inovacoes_text
    }
    justificativa
  }
}
</page-query>

<script>
import ArticleContent from "@/components/ArticleContent";
import CarouselP from "@/components/CarouselP";

export default {
  components: {
    ArticleContent,
    CarouselP,
  },
  data() {
    return {};
  },
  computed: {
    rogerScore() {
      let score = 0;

      score =
        this.$page.post.rogerscore.carne +
        this.$page.post.rogerscore.molho +
        this.$page.post.rogerscore.crosta +
        this.$page.post.rogerscore.queijo +
        this.$page.post.rogerscore.custobeneficio +
        this.$page.post.rogerscore.tempo +
        this.$page.post.rogerscore.acompanhamentos +
        this.$page.post.rogerscore.montagem;
      return score;
    },
  },
};
</script>

<style>
/* unvisited link */
a:link {
  color: red;
}

/* visited link */
a:visited {
  color: green;
}

/* mouse over link */
a:hover {
  color: hotpink;
}

/* selected link */
a:active {
  color: blue;
}
</style>
