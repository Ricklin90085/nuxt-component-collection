<template>
  <div class="container mx-auto px-4 py-12">
    <h1 class="mb-3 text-3xl font-semibold">
      元件列表：
    </h1>
    <ul class="inline-block list-disc list-inside text-indigo-500">
      <li
        v-for="i in routes"
        :key="i.name"
        class="px-2 py-1 hover:text-white hover:bg-indigo-500 rounded"
      >
        <NuxtLink :to="i.path">
          {{ i.name }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  setup () {
    const routes = [
      {
        name: 'Menu',
        path: '/menu-demo'
      }
    ]

    return {
      routes
    }
  }
})
</script>
