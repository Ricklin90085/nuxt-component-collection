<template>
  <div>
    <header class="bg-indigo-500">
      <div class="container mx-auto px-4 py-3">
        <NuxtLink
          to="/"
          class="inline-flex px-2 py-1 text-white transition-colors duration-150 rounded-md hover:bg-indigo-600"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 26 26"
            width="26"
            height="26"
            class="mr-2 fill-current"
          >
            <path fill="none" d="M0 0h24v24H0z" />
            <path
              d="M12 2c5.52 0 10 4.48 10 10s-4.48 10-10 10S2 17.52 2 12 6.48 2 12 2zm0 9V8l-4 4 4 4v-3h4v-2h-4z"
            />
          </svg>
          Back to Home
        </NuxtLink>
      </div>
    </header>
    <Nuxt />
  </div>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup () {}
})
</script>
