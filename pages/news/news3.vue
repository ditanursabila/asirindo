<script setup>
useHead({
  title: "Read News",
  meta: [
    {
      name: "description",
      content: "Read Page",
    },
  ],
});

const loading = ref(true);

onMounted(() => {
  setTimeout(() => {
    loading.value = false;
  }, 2000);
});
</script>

<template>
  <div class="h-[30vh] w-full relative mb-5 shadow-md flex items-center justify-center">
    <div>
      <div v-if="loading">
        <div v-for="n in skeletonCount" :key="n"
          class="bg-gray-500 border-2 border-gray-100 rounded-md mb-4 p-4 flex items-center">
          <div class="w-12 h-12 bg-gray-300 rounded-full mr-4"></div>
          <div class="flex-1">
            <div class="w-3/4 h-4 bg-gray-300 rounded-md mb-2"></div>
            <div class="w-1/2 h-3 bg-gray-300 rounded-md"></div>
          </div>
        </div>
      </div>

      <div v-else>
        <img src="assets/img/news3.webp" alt="foto" class="w-full h-full object-cover absolute inset-0" />
        <div class="absolute inset-0 bg-black opacity-60" />
        <div
          class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 flex flex-col items-center gap-2">
          <h1 class="text-white text-4xl font-semibold z-10 text-center">
            {{ $t("readnews") }}
          </h1>
          <h4 class="text-white text-base sm:text-lg font-semibold z-10 text-center">
            <nuxt-link to="/" class="text-white hover:text-yellow-100">{{ $t("home") }}</nuxt-link>
            >
            <nuxt-link to="/news" class="text-yellow-400">{{ $t("readnews") }}</nuxt-link>
          </h4>
        </div>
      </div>
    </div>
  </div>
  <div>
    <!-- Blog Article -->
    <div class="max-w-3xl px-4 pt-6 lg:pt-10 pb-12 sm:px-6 lg:px-8 mx-auto">
      <div class="max-w-2xl">
        
        <div class="space-y-5 md:space-y-8">
          <div class="space-y-3">
            <h2 class="text-2xl font-bold md:text-3xl">
               {{ $t("titleDetail2") }}
            </h2>

            <p class="text-lg text-gray-800">
               {{ $t("excerpt2") }}
            </p>
          </div>

          <figure>
            <img class="w-full object-cover rounded-xl" src="/assets/img/news2.jpg" alt="Blog Image" />
          </figure>

          <p class="text-lg text-gray-800">
             {{ $t("contentDetail2") }}
          </p>
        </div>
       
      </div>
    </div>
    <!-- End Blog Article -->
  </div>
</template>