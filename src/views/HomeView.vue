<script setup>
</script>

<template>
  <main class="max-w-7xl p-8 mx-auto">
    <div class="flex flex-row items-center justify-between flex-wrap gap-y-3">
      <div class="flex flex-col gap-y-3">
        <sub class="text-sm">Eliana Dantas</sub>
        <h1 class="text-3xl font-medium max-w-sm">EMPREENDIMENTOS DISPONÍVEIS EM TODA SÃO PAULO:</h1>
      </div>

      <p class="max-w-sm">Encontre seu novo estilo de vida com Eliana Dantas, corretora de imóveis em toda São Paulo. Eliana Dantas é uma corretora de imóveis experiente que pode ajudá-lo a encontrar a casa dos seus sonhos em São Paulo.</p>
    </div>

    <div class="mt-4 w-96 max-w-full h-48 bg-gray-600 bg-[url('../assets/1-small.jpg')] bg-no-repeat bg-cover bg-center rounded-lg shadow-md overflow-hidden">
      <img class="w-96 max-w-full h-48 object-cover" v-show="isLoaded" @load="onImgLoad()" src="https://erickcintra.sirv.com/b1.webp"  alt="">
    </div>
  </main>
</template>


<script>
export default {
  data() {
    return {
      isLoaded: false,
    }
  },
  methods: {
    onImgLoad() {
      return this.isLoaded = true
    }
  }
}
</script>