<template>
  <div>
    <div class="bg-purple-800 p-6">
      <div class="bg-white flex flex-col font-sans">
        <div class="container mx-auto px-8">
          <Header />
          <main
            class="flex flex-col-reverse sm:flex-row jusitfy-between items-center py-12"
          >
            <div
              class="sm:w-3/5 flex flex-col items-center sm:items-start text-center sm:text-left"
            >
              <img src="/hero-image.svg" />
            </div>
            <div class="mb-16 sm:mb-0 mt-8 sm:mt-0 sm:w-2/5 sm:pl-12">
              <nuxt />
            </div>
          </main>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "~/components/Header.vue";
export default {
  name: "AuthLayout",
  components: { Header },
};
</script>
