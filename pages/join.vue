<template>
  <!-- component -->
  <div class="bg-purple-800 p-6">
    <div class="bg-white flex flex-col font-sans">
      <div class="container mx-auto px-8">
        <header
          class="flex flex-col sm:flex-row items-center justify-between py-6 relative"
        >
          <h3 class="text-2xl font-bold uppercase text-blue-900">
            EnKayne Whiteboard
          </h3>
          <nav class="hidden md:flex text-lg">
            <a
              href="#"
              class="bg-purple-200 hover:bg-purple-300 rounded-full uppercase text-purple-700 py-3 px-6"
              >Sign Up</a
            >
          </nav>
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
              You are about to join a Whiteboard Session
            </p>
            <button
              @click="joinWhiteboard"
              class="bg-purple-600 hover:bg-purple-400 py-3 px-6 uppercase text-lg font-bold text-white rounded-full"
            >
              Join
            </button>
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
export default {
  computed: {
    channelId() {
      return this.$route.query.channel;
    },
  },
  methods: {
    joinWhiteboard() {
      if (!this.channelId) {
        console.error("unable to obtain channel name");
        return;
      }
      const joinURL = `/app?channel=${this.channelId}&mode=join`;
      this.$router.replace(joinURL);
    },
  },
};
</script>
