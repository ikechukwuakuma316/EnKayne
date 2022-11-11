<template>
  <div>
    <header
      class="flex flex-col sm:flex-row items-center justify-between py-6 relative"
    >
      <h3 class="text-2xl font-bold uppercase text-blue-900">
        EnKayne Whiteboard
      </h3>
      <section v-if="!isLoggedIn" class="flex space-x-3">
        <nav class="hidden md:flex text-lg">
          <router-link
            to="/auth/login"
            class="bg-purple-200 hover:bg-purple-300 rounded-full uppercase text-purple-700 py-3 px-6"
            >Login</router-link
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
      <section v-else class="flex space-x-3">
        <nav class="hidden md:flex text-lg">
          <a
            to="#"
            @click="logout"
            class="bg-purple-200 hover:bg-purple-300 rounded-full uppercase text-purple-700 py-3 px-6"
            >Logout
          </a>
        </nav>
      </section>

      <button class="flex md:hidden flex-col absolute top-0 right-0 p-4 mt-5">
        <span class="w-5 h-px mb-1 bg-orange-500"></span>
        <span class="w-5 h-px mb-1 bg-orange-500"></span>
        <span class="w-5 h-px mb-1 bg-orange-500"></span>
      </button>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header",
  methods: {
    logout() {
      if (this.isLoggedIn) {
        localStorage.removeItem("user");
        setTimeout(() => {
          history.go(-1);
        }, 1_000);
      }
    },
  },
  computed: {
    isLoggedIn() {
      const q = localStorage.getItem("user");
      const k = toString.call(q) === "[object String]";
      return k;
    },
  },
};
</script>
