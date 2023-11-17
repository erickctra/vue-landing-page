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
        <h1 class="text-3xl font-medium max-w-sm">EMPREENDIMENTOS DISPONÍVEIS EM TODA SÃO PAULO:</h1>
      </div>

      <p class="max-w-sm">Encontre seu novo estilo de vida com Eliana Dantas, corretora de imóveis em toda São Paulo.
        Eliana Dantas é uma corretora de imóveis experiente que pode ajudá-lo a encontrar a casa dos seus sonhos em São
        Paulo.</p>
    </div>

    <div class="mt-12 flex flex-row items-center justify-center flex-wrap gap-3">


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

    <hr class="h-px mt-12 bg-neutral-800 border-0">

    <div class="mt-12 flex flex-row flex-wrap gap-12">
      <div class="flex flex-col gap-y-3 flex-1">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-4xl font-medium max-w-md">SUA PARCERIA DE CONFIANÇA NO MERCADO IMOBILIÁRIO!</h1>
        <p>CRECISP - 254502-F</p>
        <p class="max-w-sm">Explore a sofisticação da arquitetura contemporânea em nosso site, onde você encontrará
          plantas de imóveis modernos e elegantes, projetados para refletir o luxo e o conforto que você merece.
          Descubra espaços inovadores e inspiradores para transformar seus sonhos de lar perfeito em realidade.</p>
      </div>
      <div class="p-4 bg-amber-50 flex-1 rounded-lg text-neutral-700 flex flex-col gap-y-3 w-96 min-w-[22rem] max-w-[32rem] shadow-2xl mx-auto">
        <h1 class="text-3xl font-medium max-w-sm text-center mx-auto">ENCONTRE SEU NOVO ESTILO DE VIDA</h1>
        <p class="max-w-sm text-center mx-auto">Preencha o formulário abaixo para receber todas as informações sobre imóveis disponiveis</p>
<!--        TODO: make form-->
      </div>
    </div>

    <Footer/>
  </main>
</template>

