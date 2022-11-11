<template>
  <div>
    <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <div class="mb-4">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="username"
        >
          Username
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="username"
          type="text"
          placeholder="Username"
          v-model.trim="username"
        />
      </div>
      <div class="mb-6">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="password"
        >
          Password
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
          id="password"
          type="password"
          v-model.trim="password"
          placeholder="******************"
        />
        <!-- <p class="text-red-500 text-xs italic">Please choose a password.</p> -->
      </div>
      <div class="flex items-center justify-between">
        <button
          @click.prevent="checkLogin"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="button"
        >
          Sign In
        </button>
        <!-- <a
          class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800"
          href="#"
        >
          Forgot Password?
        </a> -->
      </div>
    </form>
  </div>
</template>

<script>
export default {
  layout: "AuthLayout",
  name: "AuthLogin",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    // TODO: use map instead of plain object
    // save users as a Map to support more users
    useUserStore() {
      let returnables;
      let x = localStorage.getItem("userStore");
      if (x || typeof x !== undefined) {
        returnables = JSON.parse(x);
      }
      return returnables;
    },

    checkLogin() {
      const userStore = this.useUserStore();
      if (!userStore) {
        return;
      }

      // Fake, check against form data
      const { username, password } = userStore;
      if (
        this.username.toLowerCase() === username &&
        this.password.trim() === password
      ) {
        const values = JSON.stringify({
          username: this.username,
          password: this.password,
        });
        localStorage.setItem("user", values);
        window.location.href = "/app";
        return;
      }
      alert("incorrect username & password combination");
    },
  },
};
</script>
