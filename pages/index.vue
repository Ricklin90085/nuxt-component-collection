<template>
  <div class="container mx-auto px-4 py-8 space-y-3">
    <h1 class="text-3xl font-semibold">
      Component Playground
    </h1>
    <div class="">
      <h2 class="mb-2 text-xl">
        Headless
      </h2>
      <ul class="inline-block list-disc list-inside text-indigo-500">
        <li
          v-for="i in headlessRoutes"
          :key="i.name"
          class="px-2 py-1 hover:text-white hover:bg-indigo-500 rounded"
        >
          <NuxtLink :to="i.path">
            {{ i.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
    <div>
      <h2 class="mb-2 text-xl">
        Custom
      </h2>
      <ul class="inline-block list-disc list-inside text-indigo-500">
        <li
          v-for="i in customRoutes"
          :key="i.name"
          class="px-2 py-1 hover:text-white hover:bg-indigo-500 rounded"
        >
          <NuxtLink :to="i.path">
            {{ i.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  setup() {
    const headlessRoutes = [
      {
        name: 'Menu',
        path: '/menu-demo'
      },
      {
        name: 'Popover',
        path: '/popover-demo'
      }
    ]
    const customRoutes = [
      {
        name: 'Editor',
        path: '/editor-demo'
      }
    ]

    return {
      headlessRoutes,
      customRoutes
    }
  }
})
</script>
