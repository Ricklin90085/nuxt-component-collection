<template>
  <div class="container mx-auto px-4 py-12">
    <Popover class="relative inline-block">
      <PopoverButton
        class="inline-flex items-center px-2 py-1 text-white bg-indigo-500 rounded"
      >
        Solutions
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
      </PopoverButton>
      <PopoverPanel
        class="absolute left-0 w-96 p-4 mt-3 divide-y divide-gray-100 rounded shadow"
      >
        <ul class="flex flex-wrap -mx-2">
          <li
            v-for="i in 4"
            :key="i"
            class="w-1/2 px-2 mb-2 rounded-md cursor-pointer hover:bg-indigo-500 hover:text-white"
          >
            <div class="flex py-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                width="24"
                height="24"
                class="mr-2 fill-current"
              >
                <path fill="none" d="M0 0h24v24H0z" />
                <path
                  d="M13 1l.001 3.062A8.004 8.004 0 0 1 19.938 11H23v2l-3.062.001a8.004 8.004 0 0 1-6.937 6.937L13 23h-2v-3.062a8.004 8.004 0 0 1-6.938-6.937L1 13v-2h3.062A8.004 8.004 0 0 1 11 4.062V1h2zm-1 5a6 6 0 1 0 0 12 6 6 0 0 0 0-12zm0 4a2 2 0 1 1 0 4 2 2 0 0 1 0-4z"
                />
              </svg>
              Solution {{ i }}
            </div>
          </li>
        </ul>
      </PopoverPanel>
    </Popover>
  </div>
</template>

<script>
export default {}
</script>

<style></style>
