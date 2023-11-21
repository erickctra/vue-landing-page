<script setup>
import Thumbnail from "@/components/thumbnail/Thumbnail.vue";
import Footer from "@/components/Footer.vue";
import Skeleton from "@/components/thumbnail/Skeleton.vue";

import LazyComponent from 'v-lazy-component'
import Form from "@/components/Form.vue";
</script>

<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto">
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
      isIntersected: false,
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
            vm.houseList = result.data.imoveis;
            vm.isLoading = result.data.loading;
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>

