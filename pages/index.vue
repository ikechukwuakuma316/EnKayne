<template>
  <!-- component -->
  <div class="bg-purple-800 p-6">
    <div class="bg-white flex flex-col font-sans">
      <div class="container mx-auto px-8">
        <!-- header here -->
        <Header />

        <main
          class="flex flex-col-reverse sm:flex-row jusitfy-between items-center py-12"
        >
          <div
            class="sm:w-2/5 flex flex-col items-center sm:items-start text-center sm:text-left"
          >
            <h1
              class="uppercase text-6xl text-blue-900 font-bold leading-none tracking-wide mb-2"
            >
              Enkayne
            </h1>
            <h2
              class="uppercase text-4xl text-orange-500 text-secondary tracking-widest mb-6"
            >
              Whiteboard
            </h2>
            <p class="text-gray-600 leading-relaxed mb-12">
              Enkayne (pronounced N.K.N) is a whiteboard collaborative platform
              that runs on NKN network.
            </p>
            <a
              href="/app"
              class="bg-purple-600 hover:bg-purple-400 py-3 px-6 uppercase text-lg font-bold text-white rounded-full"
              >Get Started</a
            >
          </div>

          <div class="mb-16 sm:mb-0 mt-8 sm:mt-0 sm:w-3/5 sm:pl-12">
            <img src="/hero-image.svg" />
          </div>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "~/components/Header.vue";
export default {
  name: "IndexPage",
  components: { Header },
};
</script>
