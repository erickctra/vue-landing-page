<script setup>

</script>

<template>
  <div class="flex flex-col gap-2">
    <div class="w-full max-w-sm h-48 bg-gray-600 bg-[url('../assets/1-small.jpg')] bg-no-repeat bg-cover bg-center rounded-lg shadow-md overflow-hidden">
      <img class="w-full max-w-sm h-48 object-cover" v-show="isLoaded" @load="onImgLoad()" src="https://erickcintra.sirv.com/b1.webp"  alt="..." loading="lazy">
    </div>
    <div class="flex flex-row gap-3">
      <p>name</p>
      <span class="inline-flex items-center rounded-md bg-neutral-800 px-2 py-1 text-xs font-medium text-gray-400 ring-1 ring-inset ring-gray-500/10">Zona Sul</span>
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
    }
  }
}
</script>