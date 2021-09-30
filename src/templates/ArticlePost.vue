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
            <span class="font-semibold">Data:</span>
            <span class="font-light ml-2 mr-5" v-text="$page.post.date" />
          </div>
          <div class="flex-block">
            <span class="font-semibold">Nota:</span>
            <span class="font-light ml-2 mr-5">{{ $page.post.nota }} </span>
          </div>
          <link
            rel="stylesheet"
            href="https://use.fontawesome.com/releases/v5.11.2/css/all.css"
          />
          <div>
            <ul class="flex justify-center">
              <li v-for="(n, index) in 4" :key="index">
                <i
                  :class="[index < +$page.post.nota[0] ? 'fa' : 'far']"
                  class="fa-star fa-sm text-yellow-500 mr-1"
                ></i>
              </li>
            </ul>
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

          <br />
          <br />
          <br />
          <br />
          ---

          <div class="pt-5">
            <strong>Observações:</strong><br />
            <div>
              <p>
                Esta é uma opinião. Os critérios das notas estão explicados na
                aba 'critérios' do site. https://parmegianologo.netlify.app/
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
    nota
    cidade
    date(format: "DD/MM/YY")
    preco
    recomendacao
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
