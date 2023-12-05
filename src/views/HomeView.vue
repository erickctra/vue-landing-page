<script setup>
import Thumbnail from "@/components/thumbnail/Thumbnail.vue";
import Footer from "@/components/Footer.vue";
import Skeleton from "@/components/thumbnail/Skeleton.vue";

import Form from "@/components/Form.vue";
</script>

<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto relative">

    <a aria-label="Entrar em contato pelo whatsapp"
        class="w-14 h-14 bg-[#9CD67D] flex items-center justify-center fixed bottom-4 right-6 rounded-full shadow-2xl"
        target="_blank"

        href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site">
      <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 23 23" fill="none">
        <path fill-rule="evenodd" clip-rule="evenodd"
              d="M16.7691 13.7829C16.483 13.6404 15.0761 12.9515 14.8139 12.8564C14.5516 12.7614 14.3608 12.7139 14.1701 12.9989C13.9793 13.2839 13.4309 13.9254 13.264 14.1155C13.0971 14.3056 12.9302 14.3294 12.644 14.1868C12.3579 14.0443 11.4359 13.7436 10.343 12.7733C9.49235 12.0182 8.91805 11.0857 8.75118 10.8006C8.58422 10.5155 8.73331 10.3614 8.87658 10.2194C9.00536 10.0918 9.1628 9.88677 9.30583 9.72045C9.4489 9.55421 9.49659 9.43535 9.59197 9.24542C9.68735 9.05529 9.63966 8.88905 9.56809 8.74654C9.49659 8.60399 8.92431 7.20223 8.68586 6.63199C8.45359 6.07675 8.2177 6.15196 8.04205 6.14315C7.87534 6.13491 7.68438 6.13315 7.49366 6.13315C7.3029 6.13315 6.99287 6.20442 6.73054 6.48944C6.46832 6.77454 5.72909 7.46355 5.72909 8.86515C5.72909 10.267 6.75438 11.621 6.89749 11.8111C7.0406 12.0012 8.91517 14.8776 11.7857 16.1111C12.4684 16.4045 13.0013 16.5797 13.4169 16.7109C14.1024 16.9277 14.7261 16.8971 15.2192 16.8238C15.769 16.7421 16.9122 16.1349 17.1506 15.4698C17.3891 14.8044 17.3891 14.2343 17.3175 14.1155C17.246 13.9967 17.0552 13.9254 16.7691 13.7829ZM11.5481 20.8776H11.5443C9.83627 20.8769 8.16107 20.4202 6.69965 19.5572L6.35206 19.3518L2.74958 20.2923L3.71112 16.7967L3.48486 16.4383C2.53205 14.9301 2.0288 13.187 2.02954 11.397C2.03164 6.17413 6.30162 1.92491 11.5519 1.92491C14.0943 1.92581 16.4841 2.91243 18.2813 4.70302C20.0783 6.4935 21.0674 8.87351 21.0664 11.4046C21.0643 16.628 16.7944 20.8776 11.5481 20.8776ZM19.6489 3.34241C17.4868 1.18814 14.6115 0.00122958 11.548 0C5.23584 0 0.0985097 5.11243 0.0959564 11.3963C0.0951327 13.4051 0.62244 15.3657 1.62459 17.0941L0 23L6.07079 21.4152C7.74351 22.3231 9.62677 22.8017 11.5434 22.8023H11.5482C17.8596 22.8023 22.9974 17.6894 23 11.4054C23.0012 8.36012 21.811 5.49663 19.6489 3.34241Z"
              fill="#F2F2F2"/>
      </svg>
    </a>
    <div class="mt-12 flex flex-row flex-wrap gap-12">
      <div class="flex flex-col basis-[14rem] pl-6 gap-y-3 flex-1">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-4xl text-white font-medium max-w-md">SUA PARCERIA DE CONFIANÇA NO MERCADO IMOBILIÁRIO!</h1>
        <p>CRECISP - 254502-F</p>
        <p class="max-w-sm">Explore a sofisticação da arquitetura contemporânea em nosso site, onde você encontrará
          plantas de imóveis modernos e elegantes, projetados para refletir o luxo e o conforto que você merece.
          Descubra espaços inovadores e inspiradores para transformar seus sonhos de lar perfeito em realidade.</p>
      </div>
      <Form/>
    </div>
    <hr class="h-px my-12 bg-white opacity-10 border-0">
    <div class="flex flex-row items-end justify-between flex-wrap gap-y-3">
      <div class="flex flex-col gap-y-3">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-3xl text-white font-medium max-w-sm">EMPREENDIMENTOS DISPONÍVEIS EM TODA SÃO PAULO:</h1>
      </div>

      <p class="max-w-sm">Encontre seu novo estilo de vida com Eliana Dantas, corretora de imóveis em toda São Paulo.
        Eliana Dantas é uma corretora de imóveis experiente que pode ajudá-lo a encontrar a casa dos seus sonhos em São
        Paulo.</p>
    </div>
    <div v-if="isLoading" class="mt-12 flex flex-row items-center justify-center flex-wrap gap-3">
      <Skeleton/>
      <Skeleton/>
      <Skeleton/>
      <Skeleton/>
      <Skeleton/>
      <Skeleton/>
      <Skeleton/>
    </div>

    <div v-else class="mt-12 flex flex-row items-center justify-center flex-wrap gap-3">
      <Thumbnail v-for="house in houseList" :house="house"/>
      <!--      <Skeleton v-for="house in houseList"/>-->
      <!--      <LazyLoaded v-for="house in houseList" />-->
    </div>

    <div class="container my-24 mx-auto md:px-6">
      <!-- Section: Design Block -->
      <section class="mb-32">
        <div class="grid gap-4 md:grid-cols-2">
          <div class="mb-6 md:mb-0">
            <h2 class="mb-6 text-3xl font-bold">Perguntas frequentes</h2>

            <p class=" max-w-sm text-neutral-500">
              Não encontrou sua resposta no FAQ?
              <a href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site"
                 class="text-primary transition duration-300 hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600">
                Entre em contato com nossa equipe de vendas.</a>.
            </p>
          </div>

          <div class="mb-6 md:mb-0">
            <p class="mb-4 font-bold">Como eu vou saber se o valor do imóvel é justo?</p>
            <p class="mb-12 text-neutral-400">
              “Basta você conversar com a Eliana Dantas sua corretora de imóveis de confiança e solicitar uma análise do
              mercado
              imobiliário daquela região. Você pode também solicitar o valor de venda dos imóveis daquele local nos
              últimos 4 ou 5 meses por exemplo. Um bom corretor de imóveis vai conseguir te repassar essas informações e
              te orientar sobre o valor justo de um imóvel.”
            </p>

            <p class="mb-4 font-bold">Quais os documentos eu preciso apresentar para comprar um imóvel?</p>
            <p class="mb-12 text-neutral-400">
              Cópia do RG,
              Cópia do CPF,
              Comprovante de Residência (xerox),
              Comprovante de estado civil (cópia),
              Carteira de trabalho (cópia),
              Extrato do FGTS (em caso de utilizá-lo para a compra do imóvel),
              Se casado, apresentar os mesmos documentos do ,
              Se for separado, apresentar a cópia da certidão de casamento com averbação,
              No caso de ser empresário apresentar declaração de imposto de renda”,
            </p>

            <p class="mb-4 font-bold">
              Vale a pena comprar um imóvel com o mercado imobiliário em “crise”?
            </p>
            <p class="mb-12 text-neutral-400">
              “Quando você escuta falar que o mercado imobiliário está em crise, normalmente é porque existe uma alta
              demanda de imóveis à venda, para uma procura pequena. Nesse sentido, se você estiver em condições de
              realizar um compra é certamente, um dos melhores momentos. Onde você pode encontrar imóvel muito bons por
              valores abaixo do convencional no mercado.”
            </p>
          </div>
        </div>
      </section>
      <!-- Section: Design Block -->
    </div>

    <div class="min-w-screen min-h-screen bg-gray-50 flex items-center justify-center py-5">
      <div class="w-full bg-white border-t border-b border-gray-200 px-5 py-16 md:py-24 text-gray-800">
        <div class="w-full max-w-6xl mx-auto">
          <div class="text-center max-w-xl mx-auto">
            <h1 class="text-6xl md:text-7xl font-bold mb-5 text-gray-600">Satisfação Garantida<br></h1>
            <h3 class="text-xl mb-5 font-light">Veja o que meus clientes tem a dizer</h3>
            <div class="text-center mb-10">
              <span class="inline-block w-1 h-1 rounded-full bg-indigo-500 ml-1"></span>
              <span class="inline-block w-3 h-1 rounded-full bg-indigo-500 ml-1"></span>
              <span class="inline-block w-40 h-1 rounded-full bg-indigo-500"></span>
              <span class="inline-block w-3 h-1 rounded-full bg-indigo-500 ml-1"></span>
              <span class="inline-block w-1 h-1 rounded-full bg-indigo-500 ml-1"></span>
            </div>
          </div>
          <div class="-mx-3 md:flex items-start">
            <div class="px-3 md:w-1/3">
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://i.pravatar.cc/100?img=1" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Karen Roberta.</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Quero expressar minha
                    gratidão à Eliana Dantas pela incrível atenção e profissionalismo. Sua dedicação em esclarecer
                    minhas dúvidas foi excepcional. O carinho com que conduz seus atendimentos faz toda a diferença.
                    Obrigado por tornar tudo tão claro e por ser tão prestativa em cada etapa do processo!
                    deleniti.<span class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://erickcintra.sirv.com/profilepics/pic3.jpg" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Lucas Henrique</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Gostaria de compartilhar
                    minha experiência maravilhosa com a corretora Eliana Dantas. Seu carinho genuíno e comprometimento
                    em oferecer um atendimento excepcional são verdadeiramente notáveis. Eliana não só esclareceu todas
                    as minhas dúvidas de forma clara e objetiva, como também o fez com uma gentileza que tornou todo o
                    processo muito mais fácil e agradável. Obrigado por sua dedicação.<span
                        class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
            </div>
            <div class="px-3 md:w-1/3">
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://erickcintra.sirv.com/profilepics/pic4.jpg" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Viviane Menezes.</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Minha experiência com a
                    corretora Eliana Dantas foi além das minhas expectativas. Sua dedicação em esclarecer minhas dúvidas
                    com tanto carinho e paciência foi notável. Eliana não apenas é uma profissional exemplar, mas também
                    transmite um cuidado genuíno por seus clientes. Sou grato pelo seu apoio e por ter facilitado todo o
                    processo com seu conhecimento e atenção especial. Obrigado, Eliana!<span
                        class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://erickcintra.sirv.com/profilepics/pic1.jpg" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Gustavo Nascimento</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Estou imensamente grato à
                    Eliana Dantas pela sua atenção e cuidado durante nosso processo de consultoria. Sua abordagem
                    atenciosa e paciente ao esclarecer minhas dúvidas foi simplesmente excepcional. Agradeço
                    profundamente pelo tempo dedicado e pelo carinho demonstrado em cada interação. Eliana é uma
                    profissional notável e faz jus ao seu excelente atendimento!
                    Culpa, iusto.<span class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
            </div>
            <div class="px-3 md:w-1/3">
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://i.pravatar.cc/100?img=5" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Gabi Neves.</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Quero expressar minha
                    sincera gratidão à Eliana Dantas pela maneira carinhosa e atenciosa com que conduziu nossas
                    conversas. Sua disposição em esclarecer minhas dúvidas com paciência e clareza foi fundamental para
                    minha compreensão. Eliana não apenas é uma excelente corretora, mas também uma pessoa incrível,
                    dedicada a oferecer o melhor atendimento possível. Muito obrigado!<span
                        class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
              <div class="w-full mx-auto rounded-lg bg-white border border-gray-200 p-5 text-gray-800 font-light mb-6">
                <div class="w-full flex mb-4 items-center">
                  <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                    <img src="https://erickcintra.sirv.com/profilepics/pic2%201.webp" alt="">
                  </div>
                  <div class="flex-grow pl-3">
                    <h6 class="font-bold text-sm uppercase text-gray-600">Rodrigo Dantas.</h6>
                  </div>
                </div>
                <div class="w-full">
                  <p class="text-sm leading-tight"><span
                      class="text-lg leading-none italic font-bold text-gray-400 mr-1">"</span>Não poderia estar mais
                    satisfeito com a assessoria prestada pela Eliana Dantas. Sua gentileza e comprometimento em
                    esclarecer todas as minhas dúvidas foram incríveis. Eliana não só é extremamente competente em seu
                    trabalho, mas também demonstra um carinho genuíno por seus clientes. Agradeço imensamente pelo seu
                    excelente atendimento e pela paciência em me ajudar em cada etapa do processo<span
                        class="text-lg leading-none italic font-bold text-gray-400 ml-1">"</span></p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <Footer/>

  </main>
</template>

<script>
import gql from 'graphql-tag'

const GET_HOUSES_THUMB = gql`
  query Assets {
    imoveis {
      id
      slug
      metragem
      tema
      zonaDoImovel
      thumbnailImage
    }
  }
`

export default {
  data() {
    return {
      isIntersected: false,
      houseList: [],
      isLoading: false,

    }
  },
  created() {
    document.body.setAttribute("data-theme", "dark")

    const vm = this
    vm.getHousesList({character: '@'})
  },
  methods: {
    getHousesList(variables = {}) {

      const vm = this
      vm.isLoading = true

      vm.$apolloProvider.defaultClient
          .query({
            query: GET_HOUSES_THUMB,
            variables: {
              ...variables
            }
          })
          .then(result => {
            vm.houseList = result.data.imoveis;
            console.log(vm.houseList);
            vm.isLoading = result.data.loading;
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>

