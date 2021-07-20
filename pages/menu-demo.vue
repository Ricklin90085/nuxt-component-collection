<template>
  <div class="px-6 py-8">
    <Menu class="relative">
      <MenuButton
        class="inline-flex items-center px-2 py-1 text-white bg-indigo-500 rounded"
      >
        Options
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-4 w-4 ml-3"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 9l-7 7-7-7"
          />
        </svg>
      </MenuButton>
      <MenuItems
        class="absolute left-0 w-56 mt-3 divide-y divide-gray-100 rounded shadow"
      >
        <div class="p-1">
          <MenuItem
            class="w-full inline-flex items-center px-2 py-2 text-sm transition-colors rounded hover:bg-indigo-500 hover:text-white"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
            Option 1
          </MenuItem>
          <MenuItem
            class="w-full inline-flex items-center px-2 py-2 text-sm transition-colors rounded hover:bg-indigo-500 hover:text-white"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
            Option 2
          </MenuItem>
        </div>
        <div class="p-1">
          <MenuItem
            class="w-full inline-flex items-center px-2 py-2 text-sm transition-colors rounded hover:bg-indigo-500 hover:text-white"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
            Option 3
          </MenuItem>
          <MenuItem
            class="w-full inline-flex items-center px-2 py-2 text-sm transition-colors rounded hover:bg-indigo-500 hover:text-white"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
            Option 4
          </MenuItem>
        </div>
      </MenuItems>
    </Menu>
  </div>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup () {}
})
</script>

<style></style>
