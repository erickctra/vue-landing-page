<script setup>
import Thumbnail from "@/components/thumbnail/Thumbnail.vue";
import Footer from "@/components/Footer.vue";
import Skeleton from "@/components/thumbnail/Skeleton.vue";
</script>

<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto">
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

      <!--      <Thumbnail/>-->
      <!--      <Thumbnail/>-->
      <!--      <Thumbnail/>-->
      <!--      <Thumbnail/>-->
      <!--      <Thumbnail/>-->
    </div>

    <div v-else class="mt-12 flex flex-row items-center justify-center flex-wrap gap-3">

            <Thumbnail v-for="house in houseList" :house="house"/>

    </div>

    <hr class="h-px mt-12 bg-neutral-800 border-0">

    <div class="mt-12 flex flex-row flex-wrap gap-12">
      <div class="flex flex-col gap-y-3 flex-1">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-4xl text-white font-medium max-w-md">SUA PARCERIA DE CONFIANÇA NO MERCADO IMOBILIÁRIO!</h1>
        <p>CRECISP - 254502-F</p>
        <p class="max-w-sm">Explore a sofisticação da arquitetura contemporânea em nosso site, onde você encontrará
          plantas de imóveis modernos e elegantes, projetados para refletir o luxo e o conforto que você merece.
          Descubra espaços inovadores e inspiradores para transformar seus sonhos de lar perfeito em realidade.</p>
      </div>
      <div
          class="p-4 bg-white flex-1 rounded-lg text-neutral-700 flex flex-col gap-y-3 w-full basis-[22rem] max-w-[32rem] shadow-2xl mx-auto">
        <h1 class="text-3xl font-medium max-w-sm text-center mx-auto">ENCONTRE SEU NOVO ESTILO DE VIDA</h1>
        <p class="max-w-sm text-center mx-auto">Preencha o formulário abaixo para receber todas as informações sobre
          imóveis disponiveis</p>
        <!--        TODO: make form-->
        <form action="#">

          <label class="flex flex-col text-sm leading-6 text-neutral-700" for="name">
            Nome*
            <input id="name" class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"  type="text" name="name" placeholder="Digite seu Nome">
          </label>
          <label class="flex flex-col text-sm leading-6 text-neutral-700" for="tel">
            Telefone*
            <input id="tel" class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"  type="text" name="tel" placeholder="Digite seu Telefone">
          </label>
          <label class="flex flex-col text-sm leading-6 text-neutral-700" for="whatsapp">
            Whatsapp*
            <input id="whatsapp" class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6"  type="text" name="tel" placeholder="Digite seu WhatsApp">
          </label>

          <div class="flex flex-row flex-wrap gap-3">
            <label class="flex flex-col flex-1 basis-44 text-sm leading-6 text-neutral-700 " for="rooms">
              Quantidade de Quartos*
              <input id="rooms" class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6" min="1" type="number" name="whatsapp" placeholder="2 dorms">
            </label>

            <label class="flex flex-col flex-1 basis-44 text-sm leading-6 text-neutral-700" for="whatsapp">
              Zona*
              <select class="block w-full bg-transparent outline-0 h-[3.75rem] rounded-md border-0 py-1.5 px-4 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-emerald-900 sm:text-sm sm:leading-6" name="" id="">
                <option value="">Zona Norte</option>
                <option value="">Zona Leste</option>
                <option value="">Zona Sul</option>
                <option value="">Zona Oeste</option>
              </select>
            </label>
          </div>

          <div class="flex flex-row gap-3 mt-2">
            <div class="flex items-center gap-x-3">
              <input id="push-everything" name="push-notifications" type="radio" class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600">
              <label for="push-everything" class="block text-sm leading-6 text-gray-900">Sem Garagem</label>
            </div>
            <div class="flex items-center gap-x-3">
              <input id="push-email" name="push-notifications" type="radio" class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600">
              <label for="push-email" class="block text-sm leading-6 text-gray-900">Com Garagem</label>
            </div>
          </div>
          <hr class="h-px my-2 bg-gray-300 border-0">
          <p class="text-sm">Ao completar o formulário, você está concordando em ser contatado exclusivamente por Eliana Dantas, atuando pelo CRECISP - 254502-F para discutir nosso produto. Valorizamos sua privacidade e usaremos suas informações apenas para fornecer informações relevantes sobre nossos produtos e serviços, adaptados às suas necessidades.</p>
          <button type="button" class="text-white mt-2 w-full h-[3.75rem] bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5  dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800">Receber mais informações</button>
        </form>
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
      zonaDoImovel
      thumbnailImage
    }
  }
`

export default {
  data() {
    return {
      houseList: [],
      isLoading: false,
    }
  },
  created() {
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
            vm.houseList = result.data.imoveis
            vm.isLoading = result.data.loading
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>

