<script setup>
defineProps({
  house: {
    id: String,
    slug: String,
    metragem: String,
    zonaDoImovel: String,
    thumbnailImage: String
  }
})
// min-w-[14rem] w-full max-w-sm h-48 bg-gray-600 bg-[url(https://erickcintra.sirv.com/thumbnails/-small.jpg')] bg-no-repeat bg-cover bg-center rounded-lg shadow-md overflow-hidden

</script>

<template>
  <div class="flex flex-col flex-1 gap-2 min-w-[20rem] max-w-sm">
    <div
        class=" min-w-[14rem] w-full max-w-sm h-48 bg-gray-600 bg-no-repeat bg-cover bg-center rounded-lg shadow-md overflow-hidden">
<!--      @load event does not work with img-->
      <img class="w-full max-w-sm h-48 object-cover" v-show="showImg" @load="onImgLoad()"
           :src="house.thumbnailImage"  alt="..." loading="lazy">
    </div>
    <div class="flex flex-row gap-3">
      <p>{{ house.slug }}</p>
      <span
          class="inline-flex items-center rounded-md bg-neutral-800 px-2 py-1 text-xs font-medium text-gray-400 ring-1 ring-inset ring-gray-500/10">{{
          house.zonaDoImovel
        }}</span>
    </div>
  </div>
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
    },
  },
  computed: {
    showImg() {
      return this.isLoaded = true
    }
  }
}
</script>