<template>
  <Layout>
    <div class="sm:w-full md:w-3/4 m-auto">
      <div class="bg-white shadow-md p-10 rounded">
        <div class="place-self-center">
          <carousel :perPage="1">
            <slide v-for="(imagem, i) in $page.post.imagens" :key="i">
              <g-image
                class="
                  h-64
                  w-full
                  lg:w-full
                  lg:h-auto
                  flex-none
                  object-cover object-center
                  rounded-t
                  lg:rounded-t-none lg:rounded-l
                  text-center
                  overflow-hidden
                "
                :src="imagem.src"
                :alt="$page.post.title"
              />
            </slide>
          </carousel>
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
import { Carousel, Slide } from "vue-carousel";

export default {
  components: {
    ArticleContent,
    Carousel,
    Slide,
  },
};
</script>

<style>
.carousel-open:checked + .carousel-item {
  position: static;
  opacity: 100;
}

.carousel-item {
  -webkit-transition: opacity 0.6s ease-out;
  transition: opacity 0.6s ease-out;
}

#carousel-1:checked ~ .control-1,
#carousel-2:checked ~ .control-2,
#carousel-3:checked ~ .control-3 {
  display: block;
}

.carousel-indicators {
  list-style: none;
  margin: 0;
  padding: 0;
  position: absolute;
  bottom: 2%;
  left: 0;
  right: 0;
  text-align: center;
  z-index: 10;
}

#carousel-1:checked
  ~ .control-1
  ~ .carousel-indicators
  li:nth-child(1)
  .carousel-bullet,
#carousel-2:checked
  ~ .control-2
  ~ .carousel-indicators
  li:nth-child(2)
  .carousel-bullet,
#carousel-3:checked
  ~ .control-3
  ~ .carousel-indicators
  li:nth-child(3)
  .carousel-bullet {
  color: #2b6cb0;
  /*Set to match the Tailwind colour you want the active one to be */
}
</style>
