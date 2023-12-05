<script setup>
import Footer from "@/components/Footer.vue";
import logo from "@/assets/logo.png";
import Form from "@/components/Form.vue";
import LazyImage from "@/components/LazyImage.vue";
import LazyComponent from "v-lazy-component";
</script>

<template>
  <main class="max-w-7xl p-8 pb-0 mx-auto main relative">

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


    <router-link
        class="py-2 px-6 h-14 bg-white text-neutral-800 font-medium flex items-center justify-center fixed bottom-4 right-24 rounded-full shadow-2xl"
        to="/">Ver outros imóveis
    </router-link>

    <div class="flex flex-row flex-wrap gap-x-16 gap-8 ">
      <div class="flex flex-col gap-y-3 basis-[260px] flex-1">
        <div v-if="isLoading" class="h-[40px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <sub v-else class="text-sm">{{ houseData.imovel.zonaDoImovel }}</sub>
        <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <h1 v-else class="text-4xl text-white font-medium max-w-md uppercase">{{ houseData.imovel.headline }}</h1>
        <p>CRECISP - 254502-F</p>
        <div v-if="isLoading" class="h-[220px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <p v-else class="max-w-sm text-sm">{{ houseData.imovel.descricao }}</p>

        <div v-if="isLoading" :style="`background-image:url(${houseData.imovel.thumbnailImage.replace('.jpg','-small.jpg')})`" class="block bg-cover bg-center rounded-md bg-no-repeat w-full min-h-[400px] h-1/3 bg-white opacity-40">
        </div>

        <div v-else class="block w-full min-h-[12rem] bg-white overflow-hidden rounded-md ring-1 ring-neutral-200">
          <img height="600" class="w-full h-full object-cover object-center" :src="houseData.imovel.foto3" alt="..." @load="firstImg = false"/>
        </div>

        <div class="flex justify-center mx-auto w-full">
          <a
              target="_blank"
              class="inline-block w-auto mx-auto self-center py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-white text-neutral-800 rounded-full hover:bg-neutral-200"
              href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site">Conheça
            Imovel</a>
        </div>


      </div>
      <Form/>
    </div>

    <img class="my-10 mix-blend-overlay mx-auto text-center" width="140" height="60" loading="lazy" :src="logo"
         alt="...">

    <lazy-component wrapper-tag="section" @intersected="() => { onScreen.infoOne = true; }">
      <div v-show="onScreen.infoOne"
           class="min-h-[22rem] w-full bg-white rounded-md flex flex-row flex-wrap gap-3 shadow-2xl overflow-hidden">
        <div class=" gap-3   flex flex-row flex-wrap justify-between p-4 flex-1 basis-[20rem] ">
          <div class="max-w-sm flex flex-col gap-3">
            <sub class="text-sm text-neutral-600">Eliana Dantas</sub>
            <h1 class="text-3xl text-neutral-800 font-medium max-w-sm uppercase">Seu próximo capítulo começa aqui.</h1>
            <p class="text-neutral-600">"Nossos imóveis oferecem o conforto que você merece, independentemente do espaço
              que você procura, para atender a todas as suas necessidades."</p>
          </div>

          <div class="mx-auto min-h-[80px] flex-1 flex flex-col justify-around basis-80 max-w-[300px]">
            <div class="mx-auto">
              <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
              <div v-else class="row text-2xl font-medium text-neutral-800 flex flex-row items-center gap-3">
                <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                      d="M20.567 4.46444C20.4809 4.39735 20.3807 4.35075 20.2739 4.32818C20.1671 4.30561 20.0566 4.30765 19.9507 4.33416L14.4586 5.70698L8.94664 2.95057C8.79307 2.87397 8.61715 2.85485 8.4507 2.89666L2.7007 4.33416C2.54521 4.37303 2.40717 4.46276 2.30852 4.58908C2.20987 4.7154 2.15627 4.87107 2.15625 5.03135V17.9688C2.15627 18.0781 2.18117 18.1858 2.22907 18.284C2.27698 18.3821 2.34662 18.4681 2.43271 18.5353C2.51879 18.6025 2.61906 18.6492 2.7259 18.6719C2.83274 18.6945 2.94334 18.6925 3.0493 18.666L8.54145 17.2932L14.0534 20.0496C14.1534 20.099 14.2634 20.1248 14.375 20.1251C14.4338 20.1251 14.4923 20.1178 14.5493 20.1035L20.2993 18.666C20.4548 18.6272 20.5928 18.5374 20.6915 18.4111C20.7901 18.2848 20.8437 18.1291 20.8438 17.9688V5.03135C20.8438 4.92203 20.8189 4.81415 20.7709 4.71591C20.723 4.61767 20.6532 4.53167 20.567 4.46444ZM9.34375 4.75643L13.6562 6.91268V18.2438L9.34375 16.0875V4.75643ZM3.59375 5.59287L7.90625 4.51475V15.9698L3.59375 17.048V5.59287ZM19.4062 17.4073L15.0938 18.4855V7.03037L19.4062 5.95225V17.4073Z"
                      fill="#343330"/>
                </svg>

                {{ houseData.imovel.metragem }}
              </div>
              <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
              <div v-else class="row text-2xl font-medium text-neutral-800 flex flex-row items-center gap-3">
                <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                      d="M21.5625 18.6879H20.125V10.3819C20.125 10.1829 20.0838 9.98613 20.0038 9.80395C19.9239 9.62177 19.807 9.45818 19.6605 9.32351L12.473 2.5421C12.4695 2.53904 12.4662 2.53574 12.4631 2.53222C12.1985 2.29156 11.8537 2.1582 11.496 2.1582C11.1383 2.1582 10.7934 2.29156 10.5288 2.53222L10.5189 2.5421L3.33949 9.32351C3.19304 9.45818 3.07615 9.62177 2.99619 9.80395C2.91624 9.98613 2.87497 10.1829 2.875 10.3819V18.6879H1.4375C1.24688 18.6879 1.06406 18.7637 0.929267 18.8984C0.794475 19.0332 0.71875 19.2161 0.71875 19.4067C0.71875 19.5973 0.794475 19.7801 0.929267 19.9149C1.06406 20.0497 1.24688 20.1254 1.4375 20.1254H21.5625C21.7531 20.1254 21.9359 20.0497 22.0707 19.9149C22.2055 19.7801 22.2812 19.5973 22.2812 19.4067C22.2812 19.2161 22.2055 19.0332 22.0707 18.8984C21.9359 18.7637 21.7531 18.6879 21.5625 18.6879ZM4.3125 10.3819L4.32238 10.3729L11.5 3.59418L18.6785 10.3711L18.6884 10.3801V18.6879H14.375V14.3754C14.375 13.9942 14.2235 13.6285 13.954 13.359C13.6844 13.0894 13.3187 12.9379 12.9375 12.9379H10.0625C9.68125 12.9379 9.31562 13.0894 9.04603 13.359C8.77645 13.6285 8.625 13.9942 8.625 14.3754V18.6879H4.3125V10.3819ZM12.9375 18.6879H10.0625V14.3754H12.9375V18.6879Z"
                      fill="#343330"/>
                </svg>

                {{ houseData.imovel.quartos }}
              </div>
            </div>

            <div class="flex flex-row flex-wrap justify-center gap-3">
              <a class="py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-neutral-800 text-white rounded-full hover:bg-neutral-900"
                 href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site">Conheça
                Imovel</a>
              <a class="py-2 px-6 font-medium underline underline-offset-8 text-neutral-950" href="">Ligar para um
                Especialista</a>
            </div>
          </div>
        </div>

        <div v-if="isLoading">...</div>
        <LazyImage class="m-4" v-else :url="houseData.imovel.foto2"/>
      </div>
    </lazy-component>

    <!--    heading-->
    <lazy-component wrapper-tag="section" @intersected="() => { onScreen.headlineTwo = true; }">
      <div v-show="onScreen.headlineTwo" class="flex flex-row mt-10 flex-wrap justify-between gap-3">
        <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>
        <h1 v-else class="text-3xl max-w-sm font-medium text-white">{{ houseData.imovel.headline2 }}</h1>

        <div v-if="isLoading" class="h-[120px] w-full bg-neutral-400 opacity-10 animate-pulse"></div>

        <p v-else class="max-w-xs">{{ houseData.imovel.descricao2 }}</p>
      </div>
    </lazy-component>

    <!--photo collection-->
    <lazy-component wrapper-tag="section" @intersected="() => { onScreen.collectionOne = true; }">
      <div v-show="onScreen.collectionOne" class="mt-10">
        <div class="flex-1 h-auto collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">
          <div v-if="isLoading">...</div>
          <LazyImage :url="houseData.imovel.foto3"/>
        </div>
        <div class="flex flex-row flex-wrap gap-3 mt-3">
          <div
              class="flex-1 basis-[18.75rem] min-h-[80px] bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200"
              v-for="img in houseData.imovel.collectionOne"
          >
            <LazyImage :url="img"/>
          </div>

        </div>
      </div>
    </lazy-component>


    <img class="my-10 mix-blend-overlay mx-auto text-center" width="140" height="60" loading="lazy" :src="logo"
         alt="...">

    <!--    house info-->
    <div class="bg-white p-4 rounded-md shadow-2xl flex flex-row flex-wrap justify-between">
      <div class="flex flex-col gap-3 basis-[18rem]">
        <sub class="text-sm text-neutral-600">Imóvel</sub>
        <h1 class="text-3xl text-neutral-800 font-medium max-w-xs uppercase">Informações sobre o imóvel:</h1>
        <p class="text-neutral-800 flex flex-row items-center gap-3">
          <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
            <path
                d="M28.7076 9.70745L12.7076 25.7074C12.6147 25.8004 12.5044 25.8742 12.383 25.9245C12.2616 25.9748 12.1315 26.0007 12.0001 26.0007C11.8687 26.0007 11.7385 25.9748 11.6171 25.9245C11.4957 25.8742 11.3854 25.8004 11.2926 25.7074L4.29257 18.7074C4.10493 18.5198 3.99951 18.2653 3.99951 17.9999C3.99951 17.7346 4.10493 17.4801 4.29257 17.2924C4.48021 17.1048 4.7347 16.9994 5.00007 16.9994C5.26543 16.9994 5.51993 17.1048 5.70757 17.2924L12.0001 23.5862L27.2926 8.29245C27.4802 8.1048 27.7347 7.99939 28.0001 7.99939C28.2654 7.99939 28.5199 8.1048 28.7076 8.29245C28.8952 8.48009 29.0006 8.73458 29.0006 8.99995C29.0006 9.26531 28.8952 9.51981 28.7076 9.70745Z"
                fill="#343330"/>
          </svg>
          Area de lazer completa
        </p>
        <p class="text-neutral-800 flex flex-row items-center gap-3">
          <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
            <path
                d="M28.7076 9.70745L12.7076 25.7074C12.6147 25.8004 12.5044 25.8742 12.383 25.9245C12.2616 25.9748 12.1315 26.0007 12.0001 26.0007C11.8687 26.0007 11.7385 25.9748 11.6171 25.9245C11.4957 25.8742 11.3854 25.8004 11.2926 25.7074L4.29257 18.7074C4.10493 18.5198 3.99951 18.2653 3.99951 17.9999C3.99951 17.7346 4.10493 17.4801 4.29257 17.2924C4.48021 17.1048 4.7347 16.9994 5.00007 16.9994C5.26543 16.9994 5.51993 17.1048 5.70757 17.2924L12.0001 23.5862L27.2926 8.29245C27.4802 8.1048 27.7347 7.99939 28.0001 7.99939C28.2654 7.99939 28.5199 8.1048 28.7076 8.29245C28.8952 8.48009 29.0006 8.73458 29.0006 8.99995C29.0006 9.26531 28.8952 9.51981 28.7076 9.70745Z"
                fill="#343330"/>
          </svg>
          Academia
        </p>
      </div>

      <div class="flex flex-row flex-wrap flex-1 min-w-[200px] gap-4 mt-4">
        <div v-for="house in houseData.imovel.imovelDescricao"
             class="ring-1 ring-neutral-300 p-4 rounded-md flex flex-1 basis-[200px] flex-col gap-4 flex-wrap justify-between">
          <p class="text-neutral-800 flex flex-row items-center gap-3">
            <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                  d="M20.567 4.46444C20.4809 4.39735 20.3807 4.35075 20.2739 4.32818C20.1671 4.30561 20.0566 4.30765 19.9507 4.33416L14.4586 5.70698L8.94664 2.95057C8.79307 2.87397 8.61715 2.85485 8.4507 2.89666L2.7007 4.33416C2.54521 4.37303 2.40717 4.46276 2.30852 4.58908C2.20987 4.7154 2.15627 4.87107 2.15625 5.03135V17.9688C2.15627 18.0781 2.18117 18.1858 2.22907 18.284C2.27698 18.3821 2.34662 18.4681 2.43271 18.5353C2.51879 18.6025 2.61906 18.6492 2.7259 18.6719C2.83274 18.6945 2.94334 18.6925 3.0493 18.666L8.54145 17.2932L14.0534 20.0496C14.1534 20.099 14.2634 20.1248 14.375 20.1251C14.4338 20.1251 14.4923 20.1178 14.5493 20.1035L20.2993 18.666C20.4548 18.6272 20.5928 18.5374 20.6915 18.4111C20.7901 18.2848 20.8437 18.1291 20.8438 17.9688V5.03135C20.8438 4.92203 20.8189 4.81415 20.7709 4.71591C20.723 4.61767 20.6532 4.53167 20.567 4.46444ZM9.34375 4.75643L13.6562 6.91268V18.2438L9.34375 16.0875V4.75643ZM3.59375 5.59287L7.90625 4.51475V15.9698L3.59375 17.048V5.59287ZM19.4062 17.4073L15.0938 18.4855V7.03037L19.4062 5.95225V17.4073Z"
                  fill="#343330"/>
            </svg>
            {{ house.metragem }}
          </p>
          <p class="text-neutral-800 flex flex-row items-center gap-3">
            <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                  d="M21.5625 18.6879H20.125V10.3819C20.125 10.1829 20.0838 9.98613 20.0038 9.80395C19.9239 9.62177 19.807 9.45818 19.6605 9.32351L12.473 2.5421C12.4695 2.53904 12.4662 2.53574 12.4631 2.53222C12.1985 2.29156 11.8537 2.1582 11.496 2.1582C11.1383 2.1582 10.7934 2.29156 10.5288 2.53222L10.5189 2.5421L3.33949 9.32351C3.19304 9.45818 3.07615 9.62177 2.99619 9.80395C2.91624 9.98613 2.87497 10.1829 2.875 10.3819V18.6879H1.4375C1.24688 18.6879 1.06406 18.7637 0.929267 18.8984C0.794475 19.0332 0.71875 19.2161 0.71875 19.4067C0.71875 19.5973 0.794475 19.7801 0.929267 19.9149C1.06406 20.0497 1.24688 20.1254 1.4375 20.1254H21.5625C21.7531 20.1254 21.9359 20.0497 22.0707 19.9149C22.2055 19.7801 22.2812 19.5973 22.2812 19.4067C22.2812 19.2161 22.2055 19.0332 22.0707 18.8984C21.9359 18.7637 21.7531 18.6879 21.5625 18.6879ZM4.3125 10.3819L4.32238 10.3729L11.5 3.59418L18.6785 10.3711L18.6884 10.3801V18.6879H14.375V14.3754C14.375 13.9942 14.2235 13.6285 13.954 13.359C13.6844 13.0894 13.3187 12.9379 12.9375 12.9379H10.0625C9.68125 12.9379 9.31562 13.0894 9.04603 13.359C8.77645 13.6285 8.625 13.9942 8.625 14.3754V18.6879H4.3125V10.3819ZM12.9375 18.6879H10.0625V14.3754H12.9375V18.6879Z"
                  fill="#343330"/>
            </svg>
            {{ house.quartos }}
          </p>
          <p class="text-neutral-800 flex flex-row items-center gap-3">
            <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
              <path
                  d="M30 14H28.65L25.1775 6.1875C25.0204 5.83403 24.7641 5.53372 24.4397 5.32296C24.1153 5.11219 23.7368 5 23.35 5H8.65C8.26317 5 7.88465 5.11219 7.56029 5.32296C7.23593 5.53372 6.97965 5.83403 6.8225 6.1875L3.35 14H2C1.73478 14 1.48043 14.1054 1.29289 14.2929C1.10536 14.4804 1 14.7348 1 15C1 15.2652 1.10536 15.5196 1.29289 15.7071C1.48043 15.8946 1.73478 16 2 16H3V26C3 26.5304 3.21071 27.0391 3.58579 27.4142C3.96086 27.7893 4.46957 28 5 28H8C8.53043 28 9.03914 27.7893 9.41421 27.4142C9.78929 27.0391 10 26.5304 10 26V24H22V26C22 26.5304 22.2107 27.0391 22.5858 27.4142C22.9609 27.7893 23.4696 28 24 28H27C27.5304 28 28.0391 27.7893 28.4142 27.4142C28.7893 27.0391 29 26.5304 29 26V16H30C30.2652 16 30.5196 15.8946 30.7071 15.7071C30.8946 15.5196 31 15.2652 31 15C31 14.7348 30.8946 14.4804 30.7071 14.2929C30.5196 14.1054 30.2652 14 30 14ZM8.65 7H23.35L26.4613 14H5.53875L8.65 7ZM8 26H5V24H8V26ZM24 26V24H27V26H24ZM27 22H5V16H27V22ZM7 19C7 18.7348 7.10536 18.4804 7.29289 18.2929C7.48043 18.1054 7.73478 18 8 18H10C10.2652 18 10.5196 18.1054 10.7071 18.2929C10.8946 18.4804 11 18.7348 11 19C11 19.2652 10.8946 19.5196 10.7071 19.7071C10.5196 19.8946 10.2652 20 10 20H8C7.73478 20 7.48043 19.8946 7.29289 19.7071C7.10536 19.5196 7 19.2652 7 19ZM21 19C21 18.7348 21.1054 18.4804 21.2929 18.2929C21.4804 18.1054 21.7348 18 22 18H24C24.2652 18 24.5196 18.1054 24.7071 18.2929C24.8946 18.4804 25 18.7348 25 19C25 19.2652 24.8946 19.5196 24.7071 19.7071C24.5196 19.8946 24.2652 20 24 20H22C21.7348 20 21.4804 19.8946 21.2929 19.7071C21.1054 19.5196 21 19.2652 21 19Z"
                  fill="#343330"/>
            </svg>
            {{ house.vagas }}
          </p>
        </div>
      </div>
    </div>


    <div class="flex justify-center mx-auto w-full h-full">
      <a
          target="_blank"
          class="inline-block w-auto my-10 mx-auto self-center py-2 px-6 ring-1 shadow-2xl ring-neutral-400 font-medium bg-white text-neutral-800 rounded-full hover:bg-neutral-200"
          href="https://api.whatsapp.com/send?phone=5511996048780&text=Ol%C3%A1%2C%20gostaria%20de%20falar%20sobre%20um%20dos%20imoveis%20em%20seu%20site">Conheça
        Imovel</a>
    </div>

    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between gap-3">
      <h1 class="text-3xl max-w-sm font-medium text-white uppercase">SUA MOBILIDADE É IMPORTANTE PARA NÓS.</h1>
      <p class="max-w-xs">Este imóvel exclusivo combina acesso conveniente a centros urbanos, serviços e natureza,
        proporcionando o equilíbrio perfeito entre comodidade e serenidade. Sua localização estratégica redefine a
        praticidade, tornando-o não apenas uma propriedade, mas um estilo de vida desejado.</p>
    </div>

    <!--    location-->
    <div class="flex flex-row mt-20 flex-wrap gap-6 px-4">
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
            <path
                d="M30.125 8.7075L27.7075 6.2925C27.5199 6.10486 27.2654 5.99944 27 5.99944C26.7346 5.99944 26.4801 6.10486 26.2925 6.2925C26.1049 6.48014 25.9994 6.73464 25.9994 7C25.9994 7.26536 26.1049 7.51986 26.2925 7.7075L28.7075 10.125C28.8941 10.3118 28.9992 10.5648 29 10.8287V21C29 21.2652 28.8946 21.5196 28.7071 21.7071C28.5196 21.8946 28.2652 22 28 22C27.7348 22 27.4804 21.8946 27.2929 21.7071C27.1054 21.5196 27 21.2652 27 21V16C27 15.2044 26.6839 14.4413 26.1213 13.8787C25.5587 13.3161 24.7956 13 24 13H22V7C22 6.20435 21.6839 5.44129 21.1213 4.87868C20.5587 4.31607 19.7956 4 19 4H9C8.20435 4 7.44129 4.31607 6.87868 4.87868C6.31607 5.44129 6 6.20435 6 7V26H4C3.73478 26 3.48043 26.1054 3.29289 26.2929C3.10536 26.4804 3 26.7348 3 27C3 27.2652 3.10536 27.5196 3.29289 27.7071C3.48043 27.8946 3.73478 28 4 28H24C24.2652 28 24.5196 27.8946 24.7071 27.7071C24.8946 27.5196 25 27.2652 25 27C25 26.7348 24.8946 26.4804 24.7071 26.2929C24.5196 26.1054 24.2652 26 24 26H22V15H24C24.2652 15 24.5196 15.1054 24.7071 15.2929C24.8946 15.4804 25 15.7348 25 16V21C25 21.7956 25.3161 22.5587 25.8787 23.1213C26.4413 23.6839 27.2044 24 28 24C28.7956 24 29.5587 23.6839 30.1213 23.1213C30.6839 22.5587 31 21.7956 31 21V10.8287C31.0015 10.4349 30.9249 10.0447 30.7748 9.68057C30.6246 9.31648 30.4037 8.98575 30.125 8.7075ZM8 26V7C8 6.73478 8.10536 6.48043 8.29289 6.29289C8.48043 6.10536 8.73478 6 9 6H19C19.2652 6 19.5196 6.10536 19.7071 6.29289C19.8946 6.48043 20 6.73478 20 7V26H8ZM18 14C18 14.2652 17.8946 14.5196 17.7071 14.7071C17.5196 14.8946 17.2652 15 17 15H11C10.7348 15 10.4804 14.8946 10.2929 14.7071C10.1054 14.5196 10 14.2652 10 14C10 13.7348 10.1054 13.4804 10.2929 13.2929C10.4804 13.1054 10.7348 13 11 13H17C17.2652 13 17.5196 13.1054 17.7071 13.2929C17.8946 13.4804 18 13.7348 18 14Z"
                fill="#343330"/>
          </svg>
        </div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">ACESSIBILIDADE A TRANSPORTE E POSTOS DE GASOLINA</h2>
          <p>Este imóvel oferece fácil acesso ao transporte público, economizando tempo e dinheiro em deslocamentos.</p>
        </div>
      </div>
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
            <path
                d="M27.7675 7.35875C27.6736 7.24642 27.5562 7.15607 27.4236 7.09408C27.291 7.03209 27.1464 6.99998 27 7H6.835L6.22375 3.6425C6.14003 3.18167 5.89723 2.76484 5.53767 2.46468C5.17812 2.16452 4.72462 2.00007 4.25625 2H2C1.73478 2 1.48043 2.10536 1.29289 2.29289C1.10536 2.48043 1 2.73478 1 3C1 3.26522 1.10536 3.51957 1.29289 3.70711C1.48043 3.89464 1.73478 4 2 4H4.25L7.445 21.5362C7.53911 22.0563 7.76895 22.5423 8.11125 22.945C7.63881 23.3863 7.29781 23.9498 7.12607 24.573C6.95433 25.1962 6.95856 25.8549 7.13829 26.4759C7.31801 27.0968 7.66622 27.6559 8.14428 28.0911C8.62235 28.5263 9.2116 28.8205 9.8467 28.9412C10.4818 29.062 11.1379 29.0044 11.7423 28.775C12.3467 28.5456 12.8758 28.1533 13.2708 27.6416C13.6658 27.1299 13.9114 26.5187 13.9804 25.8759C14.0493 25.2332 13.9388 24.5838 13.6613 24H19.3388C19.115 24.4684 18.9993 24.981 19 25.5C19 26.1922 19.2053 26.8689 19.5899 27.4445C19.9744 28.0201 20.5211 28.4687 21.1606 28.7336C21.8001 28.9985 22.5039 29.0678 23.1828 28.9327C23.8617 28.7977 24.4854 28.4644 24.9749 27.9749C25.4644 27.4854 25.7977 26.8617 25.9327 26.1828C26.0678 25.5039 25.9985 24.8001 25.7336 24.1606C25.4687 23.5211 25.0201 22.9744 24.4445 22.5899C23.8689 22.2053 23.1922 22 22.5 22H10.3962C10.1621 22 9.93532 21.9177 9.75554 21.7677C9.57576 21.6176 9.45436 21.4092 9.4125 21.1787L9.01625 19H23.5163C24.2188 18.9999 24.8991 18.7532 25.4384 18.303C25.9777 17.8527 26.3419 17.2275 26.4675 16.5362L27.9875 8.17875C28.0132 8.0343 28.0069 7.88596 27.9688 7.74424C27.9308 7.60253 27.8621 7.47092 27.7675 7.35875ZM12 25.5C12 25.7967 11.912 26.0867 11.7472 26.3334C11.5824 26.58 11.3481 26.7723 11.074 26.8858C10.7999 26.9993 10.4983 27.0291 10.2074 26.9712C9.91639 26.9133 9.64912 26.7704 9.43934 26.5607C9.22956 26.3509 9.0867 26.0836 9.02882 25.7926C8.97094 25.5017 9.00065 25.2001 9.11418 24.926C9.22771 24.6519 9.41997 24.4176 9.66665 24.2528C9.91332 24.088 10.2033 24 10.5 24C10.8978 24 11.2794 24.158 11.5607 24.4393C11.842 24.7206 12 25.1022 12 25.5ZM24 25.5C24 25.7967 23.912 26.0867 23.7472 26.3334C23.5824 26.58 23.3481 26.7723 23.074 26.8858C22.7999 26.9993 22.4983 27.0291 22.2074 26.9712C21.9164 26.9133 21.6491 26.7704 21.4393 26.5607C21.2296 26.3509 21.0867 26.0836 21.0288 25.7926C20.9709 25.5017 21.0007 25.2001 21.1142 24.926C21.2277 24.6519 21.42 24.4176 21.6666 24.2528C21.9133 24.088 22.2033 24 22.5 24C22.8978 24 23.2794 24.158 23.5607 24.4393C23.842 24.7206 24 25.1022 24 25.5ZM24.5 16.1787C24.458 16.4098 24.3361 16.6187 24.1555 16.7689C23.975 16.919 23.7473 17.0008 23.5125 17H8.6525L7.19875 9H25.8013L24.5 16.1787Z"
                fill="#343330"/>
          </svg>
        </div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">PROXIMIDADE A SERVIÇOS E COMODIDADES</h2>
          <p>Localizado perto de supermercados, escolas e hospitais, tornando a vida mais conveniente.</p>
        </div>
      </div>
      <div class="flex flex-col basis-44 flex-1 gap-2">
        <div class="w-12 h-12 bg-neutral-300 rounded-full flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 32 32" fill="none">
            <path
                d="M19 15H17V7H18C19.0609 7 20.0783 7.42143 20.8284 8.17157C21.5786 8.92172 22 9.93913 22 11C22 11.2652 22.1054 11.5196 22.2929 11.7071C22.4804 11.8946 22.7348 12 23 12C23.2652 12 23.5196 11.8946 23.7071 11.7071C23.8946 11.5196 24 11.2652 24 11C23.9983 9.40921 23.3657 7.88405 22.2408 6.75919C21.116 5.63433 19.5908 5.00165 18 5H17V3C17 2.73478 16.8946 2.48043 16.7071 2.29289C16.5196 2.10536 16.2652 2 16 2C15.7348 2 15.4804 2.10536 15.2929 2.29289C15.1054 2.48043 15 2.73478 15 3V5H14C12.4087 5 10.8826 5.63214 9.75736 6.75736C8.63214 7.88258 8 9.4087 8 11C8 12.5913 8.63214 14.1174 9.75736 15.2426C10.8826 16.3679 12.4087 17 14 17H15V25H13C11.9391 25 10.9217 24.5786 10.1716 23.8284C9.42143 23.0783 9 22.0609 9 21C9 20.7348 8.89464 20.4804 8.70711 20.2929C8.51957 20.1054 8.26522 20 8 20C7.73478 20 7.48043 20.1054 7.29289 20.2929C7.10536 20.4804 7 20.7348 7 21C7.00165 22.5908 7.63433 24.116 8.75919 25.2408C9.88405 26.3657 11.4092 26.9983 13 27H15V29C15 29.2652 15.1054 29.5196 15.2929 29.7071C15.4804 29.8946 15.7348 30 16 30C16.2652 30 16.5196 29.8946 16.7071 29.7071C16.8946 29.5196 17 29.2652 17 29V27H19C20.5913 27 22.1174 26.3679 23.2426 25.2426C24.3679 24.1174 25 22.5913 25 21C25 19.4087 24.3679 17.8826 23.2426 16.7574C22.1174 15.6321 20.5913 15 19 15ZM14 15C12.9391 15 11.9217 14.5786 11.1716 13.8284C10.4214 13.0783 10 12.0609 10 11C10 9.93913 10.4214 8.92172 11.1716 8.17157C11.9217 7.42143 12.9391 7 14 7H15V15H14ZM19 25H17V17H19C20.0609 17 21.0783 17.4214 21.8284 18.1716C22.5786 18.9217 23 19.9391 23 21C23 22.0609 22.5786 23.0783 21.8284 23.8284C21.0783 24.5786 20.0609 25 19 25Z"
                fill="#343330"/>
          </svg>
        </div>
        <div class="max-w-md">
          <h2 class="text-xl font-medium text-white">VALORIZAÇÃO DO IMÓVEL</h2>
          <p>Uma localização privilegiada pode aumentar o valor da propriedade com o tempo, fazendo dela um sólido
            investimento.</p>
        </div>
      </div>
    </div>

    <div class="mt-10">
      <div class="flex-1 min-h-[80px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">
        <LazyImage :url="houseData.imovel.localizacao"/>
      </div>
    </div>

    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between mt-10 gap-3">
      <h1 class="text-3xl max-w-sm font-medium text-white uppercase">Plantas <br> disponíveis:</h1>
      <p class="max-w-xs">As plantas do imóvel exibem uma qualidade excepcional, integrando-se de forma elegante ao
        design, proporcionando não apenas beleza, mas também um conforto visual notável. Cada detalhe verde foi
        cuidadosamente escolhido, conferindo ao espaço uma atmosfera acolhedora e harmoniosa.</p>
    </div>


    <!--    plantas-->
    <lazy-component wrapper-tag="section" @intersected="() => { onScreen.houseMaps = true; }">
      <div class="mt-10 flex flex-col gap-3">
        <div v-show="onScreen.houseMaps" v-for="house in houseData.imovel.planta"
             class="flex-1 min-h-[80px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">
          <LazyImage :url="house"/>
        </div>
      </div>
    </lazy-component>


    <!--    heading-->
    <div class="flex flex-row flex-wrap justify-between mt-10 gap-3">
      <h1 class="text-3xl max-w-xs font-medium text-white uppercase">PREDIO REPLETO DE CONFORTO E AREAS DE LAZER</h1>
      <p class="max-w-md">O condomínio destaca-se pela qualidade excepcional, oferecendo um conforto inigualável. Suas
        áreas de lazer são verdadeiros oásis de entretenimento, proporcionando momentos de relaxamento e diversão para
        todos os moradores.</p>
    </div>
    <!--    <Faq/>-->
    <lazy-component wrapper-tag="section" @intersected="() => { onScreen.otherPhotos = true; }">
      <div class="mt-10 flex flex-col gap-3">
        <div v-show="onScreen.otherPhotos" v-for="img in houseData.imovel.demaisFotos"
             class="flex-1 min-h-[80px] collection-big bg-neutral-300 rounded-md shadow-2xl ring-1 ring-neutral-200">
          <LazyImage :url="img"/>
        </div>
      </div>
    </lazy-component>


    <Footer/>
  </main>
</template>


<script>
import gql from 'graphql-tag'

export default {
  data() {
    return {
      isIntersected: false,
      QUERY: null,
      houseData: {},
      isLoading: false,
      firstImg: false,

      onScreen: {
        infoOne: false,
        headlineTwo: false,
        collectionOne: false,
        houseMaps: false,
        otherPhotos: false
      }
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
            thumbnailImage
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

            vm.isLoading = false;
          })
          .catch(error => {
            console.log(error)
          })
    }
  }
}
</script>