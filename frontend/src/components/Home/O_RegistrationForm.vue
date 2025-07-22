<template>
  <div class="min-h-screen bg-gray-100 flex flex-col items-center pt-10 px-4">
    <!-- Topbar -->
    <div class="w-full max-w-4xl flex justify-between items-center mb-8">
      <h1 class="text-3xl font-semibold text-dark-slate font-inter">PathFinder</h1>
      <input
        type="text"
        placeholder="Search..."
        class="input input-bordered w-64"
      />
    </div>

    <!-- Form Card -->
    <div class="bg-white p-8 rounded-xl shadow-md w-full max-w-2xl">
      <!-- Back Button -->
      <div class="pb-4">
        <button
          class="btn btn-ghost text-dark-slate"
          @click="$router.push('/loginform')"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 mr-1"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15 18l-6-6 6-6"
            />
          </svg>
          Back
        </button>
      </div>

      <!-- Heading -->
      <h2 class="text-3xl font-semibold text-dark-slate font-inter mb-6">
        Create Account
      </h2>

      <!-- Form -->
      <form>
        <div class="form-control mb-4">
          <input
            class="input input-bordered w-full"
            type="text"
            required
            placeholder="Organization Name"
            name="name"
          />
        </div>

        <div class="form-control mb-4">
          <input
            class="input input-bordered w-full"
            type="text"
            required
            placeholder="Location"
            name="location"
          />
        </div>

        <div class="form-control mb-4">
          <input
            class="input input-bordered w-full"
            type="url"
            placeholder="Website URL"
            name="websiteUrl"
          />
        </div>

        <div class="form-control mb-4">
          <input
            class="input input-bordered validator w-full"
            type="email"
            required
            placeholder="Email"
            name="emailAddress"
          />
          <p class="validator-hint hidden text-sm text-red-500">Invalid Email</p>
        </div>

        <div class="form-control mb-4">
          <input
            type="password"
            class="input input-bordered validator w-full"
            required
            placeholder="Password"
            minlength="8"
            pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
            title="Must be more than 8 characters, including number, lowercase letter, uppercase letter"
            name="Password"
          />
          <p class="validator-hint hidden text-sm text-red-500">
            Must be more than 8 characters, including number, lowercase letter, uppercase letter
          </p>
        </div>

        <div class="form-control mb-4">
          <input
            type="password"
            class="input input-bordered validator w-full"
            required
            placeholder="Confirm Password"
            minlength="8"
            pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
            title="Must be more than 8 characters, including number, lowercase letter, uppercase letter"
            name="confirmPassword"
          />
          <p class="validator-hint hidden text-sm text-red-500">Invalid Password</p>
        </div>

        <div class="form-control mb-4">
          <label class="flex items-center space-x-2 cursor-pointer">
            <input
              type="checkbox"
              class="checkbox validator"
              required
              v-model="termsAccepted"
            />
            <span>Accept all terms and conditions before creating account</span>
          </label>
        </div>

        <!-- Submit Button -->
        <div class="pt-4 flex justify-end">
          <button class="btn bg-dark-slate text-white w-1/2 hover:bg-slate-800">
            Create
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const termsAccepted = ref(false)
</script>

<style scoped>
.text-dark-slate {
  color: #2f3e46;
}
.bg-dark-slate {
  background-color: #2f3e46;
}
</style>