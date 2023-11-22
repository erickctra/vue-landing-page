<script setup>
import LazyComponent from "v-lazy-component";
import Skeleton from "@/components/thumbnail/Skeleton.vue";

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
  <lazy-component class="flex flex-1 max-w-sm basis-[18rem]" wrapper-tag="section" @intersected="Intersect">
      <router-link :to="'/casa/' + house.slug">

      <div class="flex flex-col flex-1 gap-2 ">
        <div
            class=" w-full h-48 bg-gray-600 bg-no-repeat bg-cover bg-center rounded-lg shadow-md overflow-hidden">
          <!--      @load event does not work with img-->
          <img class="w-full h-48 object-cover" v-show="isLoaded" decoding="async"
               :src="house.thumbnailImage"  alt="...">
        </div>
        <div class="flex flex-row gap-3 text-gray-200">
          <p>{{ house.slug }}</p>
          <span
              class="inline-flex items-center rounded-md bg-neutral-400 bg-opacity-10 px-2 py-1 text-xs font-medium text-gray-200 ring-1 ring-inset ring-gray-500/10">{{
              house.zonaDoImovel
            }}</span>
        </div>
      </div>

      <!-- Optional -->
      <template #placeholder>
        <Skeleton/>
      </template>
      </router-link>
  </lazy-component>
</template>


<script>
export default {
  data() {
    return {
      isLoaded: false,
    }
  },
  methods: {
    Intersect() {
      return this.isLoaded = true
    },
  }
}
</script>