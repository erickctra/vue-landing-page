<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto main">


    <div class="mt-12 flex flex-row flex-wrap gap-8 ">
      <div class="flex flex-col gap-y-3 flex-1 pl-6">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-4xl text-white font-medium max-w-md">SUA PARCERIA DE CONFIANÇA NO MERCADO IMOBILIÁRIO!</h1>
        <p>CRECISP - 254502-F</p>
        <p class="max-w-sm">Explore a sofisticação da arquitetura contemporânea em nosso site, onde você encontrará
          plantas de imóveis modernos e elegantes, projetados para refletir o luxo e o conforto que você merece.
          Descubra espaços inovadores e inspiradores para transformar seus sonhos de lar perfeito em realidade.</p>
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
            <div class="row text-2xl font-medium text-neutral-800">147m² a 194m²</div>
            <div class="row text-2xl font-medium text-neutral-800">2 a 6 quartos</div>
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

      <div class="bg-white min-h-[22rem] flex-1 basis-[36rem] m-4 rounded-md shadow-2xl"></div>
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
        class="inline-block shadow-2xl w-auto my-10 mx-auto self-center py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-white text-neutral-800 rounded-full hover:bg-neutral-200"
        href="">Conheça
      Imovel</a>
    </div>

    <!--    heading-->
    <div class="flex flex-row mt-10 flex-wrap justify-between gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white">MODERNIDADE E ACONCHEGO EM PERFEITA SINTONIA.</h1>
      <p class="max-w-md">Com ambientes espaçosos e acabamentos de alta qualidade, esta residência redefine o padrão de
        luxo. Desfrute de uma vida sofisticada em cada detalhe, onde o conforto se encontra com o design refinado. Seu
        lar dos sonhos começa aqui.</p>
    </div>

    <!--    <Faq/>-->

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

<script setup>

import Footer from "@/components/Footer.vue";
import logo from "@/assets/logo.png";
import Faq from "@/components/Faq.vue";
import Form from "@/components/Form.vue";
</script>