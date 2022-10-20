<template>
  <div>
    <div class="bg-purple-800 p-6">
      <div class="bg-white flex flex-col font-sans">
        <div class="container mx-auto px-8">
          <header
            class="flex flex-col sm:flex-row items-center justify-between py-6 relative"
          >
            <h3 class="text-2xl font-bold uppercase text-blue-900">
              EnKayne Whiteboard
            </h3>
            <section class="flex space-x-3">
              <nav class="hidden md:flex text-lg">
                <router-link
                  to="/auth/login"
                  class="bg-purple-200 hover:bg-purple-300 rounded-full uppercase text-purple-700 py-3 px-6"
                  >Sign in</router-link
                >
              </nav>
              <nav class="hidden md:flex text-lg">
                <router-link
                  to="/auth/signup"
                  class="bg-purple-200 hover:bg-purple-300 rounded-full uppercase text-purple-700 py-3 px-6"
                  >Sign Up
                </router-link>
              </nav>
            </section>
            <button
              class="flex md:hidden flex-col absolute top-0 right-0 p-4 mt-5"
            >
              <span class="w-5 h-px mb-1 bg-orange-500"></span>
              <span class="w-5 h-px mb-1 bg-orange-500"></span>
              <span class="w-5 h-px mb-1 bg-orange-500"></span>
            </button>
          </header>
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
export default {
  name: "AuthLayout",
};
</script>
