<template>
  <Layout>
    <div class="sm:w-full md:w-3/4 m-auto">
      <div class="bg-white shadow-md p-1 rounded">
        <div class="my-6">
          <VueSlickCarousel v-bind="settings">
            <div v-for="(imagem, i) in $page.post.imagens" :key="i">
              <g-image
                :key="i"
                class="
                  h-96
                  w-full
                  lg:w-full
                  lg:h-1/2
                  flex-none
                  object-cover object-center
                  rounded-t
                  lg:rounded-t-none lg:rounded-l
                  text-center
                  overflow-hidden
                "
                :src="imagem.src"
                :alt="imagem.src"
              />
            </div>
          </VueSlickCarousel>
        </div>
        <div class="text-4xl font-bold">
          <spam v-text="$page.post.title" class="Article-title"></spam>
          <span> - </span>
          <spam v-text="$page.post.cidade" class="font-light"></spam>
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

        <div class="pt-5">
          <strong>Introdução:</strong><br />
          <div>
            <p>
              <!-- {{ $page.post.introducao }} -->
            </p>
          </div>
        </div>

        <div class="pt-5">
          <strong>Roger Score:</strong><br />
          <div class="pt-5">
            <span class="font-semibold"
              >Carne: {{ $page.post.rogerscore.carne }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.carne_text }}
              </p>
            </div>
            <span class="font-semibold"
              >Carne: {{ $page.post.rogerscore.crosta }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.crosta_text }}
              </p>
            </div>
            <span class="font-semibold"
              >Carne: {{ $page.post.rogerscore.queijo }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.queijo_text }}
              </p>
            </div>
            <span class="font-semibold"
              >Carne: {{ $page.post.rogerscore.molho }} / 100</span
            >
            <div>
              <p>
                {{ $page.post.rogerscore.molho_text }}
              </p>
            </div>
          </div>
          <div>
            <p></p>
            <p>Crosta: {{ $page.post.rogerscore.crosta }} / 100</p>
            <p>Queijo: {{ $page.post.rogerscore.queijo }} / 100</p>
            <p>Molho {{ $page.post.rogerscore.molho }} / 100</p>
            <p>
              Acompanhamento 1:
              {{ $page.post.rogerscore.nome_acompanhamento1 }}:
              {{ $page.post.rogerscore.acompanhamento1 }} / 100
            </p>
            <p>
              Acompanhamento 2:
              {{ $page.post.rogerscore.nome_acompanhamento2 }}:
              {{ $page.post.rogerscore.acompanhamento2 }} / 100
            </p>
            <p>Montagem: {{ $page.post.rogerscore.montagem }} / 100</p>
            <p>Tempo de preparação: {{ $page.post.rogerscore.tempo }} / 100</p>
            <p>Inovações: {{ $page.post.rogerscore.inovacoes }} / 100</p>
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
                  - Recomendado
                </ul>
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
    cidade
    date(format: "DD/MM/YY")
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
      inovacoes
      carne_text
      molho_text
      queijo_text
      crosta_text
      acompanhamento1_text
      acompanhamento2_text
      tempo_text
      custobeneficio_text
      inovacoes_text
    }
    justificativa
  }
}
</page-query>

<script>
import ArticleContent from "@/components/ArticleContent";
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  components: {
    ArticleContent,
    VueSlickCarousel,
  },
  data() {
    return {
      settings: {
        dots: true,
        dotsClass: "slick-dots custom-dot-class",
        infinite: false,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
      },
    };
  },
};
</script>

<style>
</style>
