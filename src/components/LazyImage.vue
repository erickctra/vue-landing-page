<script setup>
import LazyComponent from "v-lazy-component";

defineProps({
  url: String
})
</script>

<template>
  <lazy-component class="lazy-image overflow-hidden w-full h-full flex bg-white flex-1 basis-[36rem] rounded-md shadow-2xl" wrapper-tag="section" @intersected="Intersect">
    <img class="w-full h-full object-cover object-center" :src="url" v-show="isLoaded" alt="..." loading="lazy">

    <template #placeholder>
      <div>...</div>
    </template>
  </lazy-component>
</template>

<style scoped>
.lazy-image{
  height: auto;
}
</style>

<script>
export default {
  data() {
    return {
      isLoaded: false
    }
  },
  methods: {
    Intersect() {
      console.log('location loaded')
      return this.isLoaded = true
    },
  }
}
</script>