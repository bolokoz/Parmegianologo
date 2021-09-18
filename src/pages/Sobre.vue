<template>
  <Layout>
    <div class="container mx-auto w-3/4 py-3">
      <h1 class="font-bold text-5xl">Sobre</h1>
      <p>
        Faço avaliações de parmegianas. Meu prato preferido. Já
        provei muitos parmegianas na vida e precisava catologá-los.
      </p>
    </div>

    <div class="container mx-auto w-3/4 py-3">
      <h1 class="font-bold text-5xl">Por que?</h1>
      <p>
        Sempre quando chegava em um restaurante, novo ou não, eu pedia o
        parmegiana. Quando o prato chegava eu lembrava que já havia comido
        naquele local e o prato era ruim, inclusive havia dito que não pediria mais o
        parmegiana daquele lugar... mas no fim acabava esquecendo. O besta não pode ver parmegiana que sempre pede. Então, para eu evitar de cometer o mesmo
        erro, decidi começar a catalogar eles.
      </p>
    </div>

    <div class="container mx-auto w-3/4 py-3">
      <h1 class="font-bold text-3xl">A nota vai de um a quatro??</h1>
      <p>
        Sim, a escala é 1 a 4. Normamente usa-se 1-5 ou 1-10, mas inspirado na
        <a
          href="https://en.wikipedia.org/wiki/Glasgow_Coma_Scale"
          target="_blank"
          >escala de Glasgow
        </a>
        decidi usar 1-4, sendo:
      </p>
      <p>
        <ul>
  <li>1/4 - ruim</li>
  <li>2/4 - abaixo da média</li>
  <li>3/4 - acima da média</li>
  <li>4/4 - muito bom</li>
</ul>
      </p>
    </div>
    <div class="container mx-auto w-3/4 py-3">
      <h2 class="font-bold text-2xl">
        Nossa que escala idiota, tinha que ser de 1 a 10
      </h2>
      <p>
        Achei a escala 1-4 legal pois resume rapidamente um prato. Por ser
        uma questão subjetiva, não deve ter muitos valores. Por exemplo, se
        fosse de 1-10, um prato muito bom você teria dúvidas de colocá-lo entre
        nota 7, 8 ou 9. Raramente você daria nota 10.
      </p>
    </div>

        <div class="container mx-auto w-3/4 py-3">
      <h2 class="font-bold text-2xl">
        Gostei do projeto. Quero fazer um também
      </h2>
      <p>
        Se sua comida favorita é picanha na chapa ou você quer catalogar os melhores hamburgers vegetarianos. Fale comigo <a href="https://www.instagram.com/parmegianologo" target="_blank">no instagram</a> que eu te ensino a fazer algo idêntico. É tudo grátis. Não paga servidor e não precisa saber programação.
      </p>
      <p>
        Caso entenda um pouco de programação web (HTML, Vue.js), garfeie o projeto <a href="https://www.github.com/bolokoz/parmegianologo" target="_blank"> neste link no GitHub </a>
      </p>
    </div>

        <div class="container mx-auto w-3/4 py-3">
      <h2 class="font-bold text-2xl">
        O que é essa parte de 'ADMIN'
      </h2>
      <p>
         É por onde se acessa o CMS (content manage system, eu acho). É uma gambiarra pra não ter que abrir o código do site toda vez que precisar adicionar um prato. Se você for nerdola, eu uso o <a href="https:www.forestry.io">Forestry.io</a> como CMS. Nele você entra com suas senha e aparece como se fosse um Google Forms, já com os campos pra você preencher e adicionar as fotos do pratos. Ao terminar de adicionar o seu prato, ele acessa o <a href="https://www.github.com/bolokoz/parmegianologo">repositório no Github </a>, dá um push com os novos conteúdos e manda um sinal pro <a href="https://www.netlify.com">Netlify</a> pra fazer a build do código. Dessa forma ele gera todas páginas estaticamente e hosteia todas elas, sem precisar de um servidor.
      </p>
    </div>
  </Layout>
</template>

<script>
export default {
  data() {
    return {};
  },
  metaInfo: {
    title: "Sobre e FAQ",
  },
};
</script>

<style scoped>
a {
  color: green;
}
</style>