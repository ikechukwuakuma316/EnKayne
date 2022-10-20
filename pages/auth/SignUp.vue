<template>
  <div>
    <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
          Email Address
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="email"
          type="text"
          v-model.trim="formData.email"
          placeholder="email"
          required
        />
      </div>

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
          v-model.trim="formData.username"
          placeholder="Username"
          required
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
          v-model.trim="formData.password"
          type="password"
          placeholder="******************"
          required
        />
      </div>

      <div class="mb-6">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="password"
        >
          Confirm Password
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
          id="password"
          v-model.trim="formData.cpassword"
          type="password"
          placeholder="******************"
          required
        />
      </div>

      <div class="flex items-center justify-between">
        <button
          @click.prevent="doLogin"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="button"
        >
          Sign Up
        </button>
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
      formData: {
        email: "",
        username: "",
        password: "",
        cpassword: "",
      },
    };
  },
  methods: {
    doLogin() {
      if (Object.values(this.formData).length >= 3) {
        // fake signup, then redirect to home
        const { cpassword, password } = this.formData;
        if (password !== cpassword) {
          alert("passwords must match");
          return;
        }

        this.formData.username = this.formData.username.toLowerCase();
        this.formData.email = this.formData.email.toLowerCase();

        // convert to string against localStorage
        const values = JSON.stringify(this.formData);

        // save single user
        localStorage.setItem("user", values);

        // save to userStore
        localStorage.setItem("userStore", values);

        setTimeout(() => {
          window.location.href = "/";
        }, 1_000);
      }
    },
  },
};
</script>
