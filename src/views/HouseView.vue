<script setup>
import Footer from "@/components/Footer.vue";
import logo from "@/assets/logo.png";
import Faq from "@/components/Faq.vue";
import Form from "@/components/Form.vue";
import LazyImage from "@/components/LazyImage.vue";


</script>

<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto main">
    <div class="mt-12 flex flex-row flex-wrap gap-8 ">
      <div class="flex flex-col gap-y-3 basis-[260px] flex-1 pl-6">
        <div v-if="isLoading" class="h-[40px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <sub v-else class="text-sm">{{ houseData.imovel.zonaDoImovel }}</sub>
        <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <h1 v-else class="text-4xl text-white font-medium max-w-md uppercase">{{houseData.imovel.headline}}</h1>
        <p>CRECISP - 254502-F</p>
        <div v-if="isLoading" class="h-[220px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <p v-else class="max-w-sm">{{houseData.imovel.descricao}}</p>
      </div>
      <Form/>
    </div>

    <img class="my-10 mix-blend-overlay mx-auto text-center" width="140" height="60" loading="lazy" :src="logo"
         alt="...">

    <div class="min-h-[22rem] w-full bg-white rounded-md flex flex-row flex-wrap gap-3 shadow-2xl overflow-hidden">
      <div class="flex flex-row flex-wrap justify-between p-4 flex-1 basis-[20rem] ">
        <div class="max-w-sm flex flex-col gap-3">
          <sub class="text-sm text-neutral-600">Eliana Dantas</sub>
          <h1 class="text-3xl text-neutral-800 font-medium max-w-md uppercase">Seu próximo capítulo começa aqui.</h1>
          <p class="text-neutral-600">"Nossos imóveis oferecem o conforto que você merece, independentemente do espaço
            que você procura, para atender a todas as suas necessidades."</p>
        </div>

        <div class="mx-auto min-h-[200px] flex-1 flex flex-col justify-around basis-80 max-w-[300px]">
          <div class="mx-auto">
            <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
            <div v-else class="row text-2xl font-medium text-neutral-800">{{houseData.imovel.metragem}}</div>
            <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
            <div v-else class="row text-2xl font-medium text-neutral-800">{{houseData.imovel.quartos }}</div>
          </div>

          <div class="flex flex-row flex-wrap justify-center gap-3">
            <a class="py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-neutral-800 text-white rounded-full hover:bg-neutral-900"
               href="">Conheça
              Imovel</a>
            <a class="py-2 px-6 font-medium underline underline-offset-8 text-neutral-950" href="">Ligar para um
              Especialista</a>
          </div>
        </div>
      </div>

      <div v-if="isLoading">...</div>
      <LazyImage v-else :url="houseData.imovel.localizacao"/>
    </div>

    <!--    heading-->
    <div class="flex flex-row mt-10 flex-wrap justify-between gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white">MODERNIDADE E ACONCHEGO EM PERFEITA SINTONIA.</h1>
      <p class="max-w-md">Com ambientes espaçosos e acabamentos de alta qualidade, esta residência redefine o padrão de
        luxo. Desfrute de uma vida sofisticada em cada detalhe, onde o conforto se encontra com o design refinado. Seu
        lar dos sonhos começa aqui.</p>
    </div>
    <!--photo collection-->
    <div class="mt-10">
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
      <div class="flex flex-row flex-wrap gap-3 mt-3">
        <div
            class="flex-1 basis-[18.75rem] min-h-[200px] bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200"></div>
        <div
            class="flex-1 basis-[18.75rem] min-h-[200px] bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200"></div>
        <div
            class="flex-1 basis-[18.75rem] min-h-[200px] bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200"></div>
      </div>
    </div>

    <img class="my-10 mix-blend-overlay mx-auto text-center" width="140" height="60" loading="lazy" :src="logo"
         alt="...">

    <!--    house info-->
    <div class="bg-white p-4 rounded-md shadow-2xl flex flex-row flex-wrap justify-between">
      <div class="flex flex-col gap-3 basis-[18rem]">
        <sub class="text-sm text-neutral-600">Imóvel</sub>
        <h1 class="text-3xl text-neutral-800 font-medium max-w-xs uppercase">Informações sobre o imóvel:</h1>
        <p class="text-neutral-800">Area de lazer completa</p>
        <p class="text-neutral-800">Academia</p>
      </div>

      <div class="flex flex-row flex-wrap flex-1 gap-4 mt-4">
        <div
            class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800">planta 147m²</p>
          <p class="text-neutral-800">3 suites</p>
          <p class="text-neutral-800">2 vagas</p>
        </div>
        <div
            class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800">planta 147m²</p>
          <p class="text-neutral-800">3 suites</p>
          <p class="text-neutral-800">2 vagas</p>
        </div>
        <div
            class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800">planta 147m²</p>
          <p class="text-neutral-800">3 suites</p>
          <p class="text-neutral-800">2 vagas</p>
        </div>
        <div
            class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800">planta 147m²</p>
          <p class="text-neutral-800">3 suites</p>
          <p class="text-neutral-800">2 vagas</p>
        </div>
        <div
            class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800">planta 147m²</p>
          <p class="text-neutral-800">3 suites</p>
          <p class="text-neutral-800">2 vagas</p>
        </div>
      </div>
    </div>


    <div class="flex justify-center mx-auto w-full h-full">
      <a
          target="_blank"
          class="inline-block w-auto my-10 mx-auto self-center py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-white text-neutral-800 rounded-full hover:bg-neutral-200"
          href="">Conheça
        Imovel</a>
    </div>

    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white">MODERNIDADE E ACONCHEGO EM PERFEITA SINTONIA.</h1>
      <p class="max-w-md">Com ambientes espaçosos e acabamentos de alta qualidade, esta residência redefine o padrão de
        luxo. Desfrute de uma vida sofisticada em cada detalhe, onde o conforto se encontra com o design refinado. Seu
        lar dos sonhos começa aqui.</p>
    </div>

    <!--    location-->
    <div class="flex flex-row mt-20 flex-wrap gap-6 px-4">
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">icon</div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">ACESSIBILIDADE A TRANSPORTE E POSTOS DE GASOLINA</h2>
          <p>Este imóvel oferece fácil acesso ao transporte público, economizando tempo e dinheiro em deslocamentos.</p>
        </div>
      </div>
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">icon</div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">PROXIMIDADE A SERVIÇOS E COMODIDADES</h2>
          <p>Localizado perto de supermercados, escolas e hospitais, tornando a vida mais conveniente.</p>
        </div>
      </div>
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">icon</div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">VALORIZAÇÃO DO IMÓVEL</h2>
          <p>Uma localização privilegiada pode aumentar o valor da propriedade com o tempo, fazendo dela um sólido
            investimento.</p>
        </div>
      </div>
    </div>

    <div class="mt-10">
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
    </div>

    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between mt-10 gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white uppercase">Plantas <br> disponíveis:</h1>
      <p class="max-w-md">As plantas do imóvel exibem uma qualidade excepcional, integrando-se de forma elegante ao
        design, proporcionando não apenas beleza, mas também um conforto visual notável. Cada detalhe verde foi
        cuidadosamente escolhido, conferindo ao espaço uma atmosfera acolhedora e harmoniosa.</p>
    </div>


    <!--    plantas-->
    <div class="mt-10 flex flex-col gap-3">
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
    </div>

    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between mt-10 gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white uppercase">PREDIO REPLETO DE CONFORTO E AREAS DE LAZER</h1>
      <p class="max-w-md">O condomínio destaca-se pela qualidade excepcional, oferecendo um conforto inigualável. Suas
        áreas de lazer são verdadeiros oásis de entretenimento, proporcionando momentos de relaxamento e diversão para
        todos os moradores.</p>
    </div>
    <!--    <Faq/>-->
    <div class="mt-10 flex flex-col gap-3">
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
      <div class="flex-1 min-h-[400px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">

      </div>
    </div>

    <Footer/>
  </main>
</template>

<style>
@media (max-width: 675px) {
  .collection-big {
    min-height: 200px !important;
  }
}
</style>

<script>
import gql from 'graphql-tag'

export default {
  data() {
    return {
      isIntersected: false,
      QUERY: null,
      houseData: {},
      isLoading: false,
    }
  },
  created() {
    document.body.setAttribute("data-theme", `${this.$route.params.theme}`)

    this.QUERY = gql`
        query Imoveis {
          imovel(where: {slug: "${this.$route.params.slug}"}) {
            academia
            areaLazer
            collectionOne
            demaisFotos
            descricao
            descricao2
            metragem
            foto1
            foto2
            foto3
            fotoCapa
            garagem
            headline
            headline2
            imovelNaPlanta
            localizacao
            planta
            quartos
            slug
            tema
            tituloImovel
            zonaDoImovel
            imovelDescricao {
              ... on ImovelDescricao {
                id
                metragem
                quartos
                stage
                vagas
              }
            }
          }
        }
      `

    const vm = this;
    vm.getHouseData({character: '@'})
  },
  methods: {
    getHouseData(variables = {}) {
      const vm = this
      vm.isLoading = true

      vm.$apolloProvider.defaultClient
          .query({
            query: vm.QUERY,
            variables: {
              ...variables
            }
          })
          .then(result => {
            vm.houseData = result.data;
            vm.isLoading = result.data.loading;
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>