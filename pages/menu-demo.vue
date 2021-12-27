<template>
  <div class="container mx-auto px-6 py-8">
    <Menu class="relative inline-block">
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
    <Menu class="relative inline-block">
      <MenuInput
        v-model="selectedValue"
        class="inline-flex items-center px-2 py-1 text-white bg-indigo-500 rounded"
      />
      <MenuItems
        class="absolute left-0 w-56 max-h-52 mt-3 divide-y divide-gray-100 rounded shadow overflow-y-auto"
      >
        <MenuItem
          v-for="option in filterOptions"
          :key="option"
          class="w-full inline-flex items-center px-2 py-2 text-sm transition-colors rounded hover:bg-indigo-500 hover:text-white"
          @click.native="selectedValue = option"
        >
          {{ option }}
        </MenuItem>
      </MenuItems>
    </Menu>
  </div>
</template>

<script>
import { computed, defineComponent, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const selectedValue = ref('')
    const options = [
      '一江街',
      '中原街',
      '中山北路一段',
      '中山北路三段',
      '中山北路二段',
      '中山北路四段',
      '五常街',
      '伊通街',
      '內湖路一段',
      '八德路二段',
      '劍南路',
      '北安路',
      '南京東路一段',
      '南京東路三段',
      '南京東路二段',
      '南京西路',
      '合江街',
      '吉林路',
      '四平街',
      '基湖路',
      '堤頂大道二段',
      '大直街',
      '天津街',
      '天祥路',
      '安東街',
      '崇實路',
      '市民大道三段',
      '市民大道二段',
      '建國北路一段',
      '建國北路三段',
      '建國北路二段',
      '建國南路一段',
      '復興北路',
      '復興南路一段',
      '德惠街',
      '撫順街',
      '敬業一路',
      '敬業三路',
      '敬業二路',
      '敬業四路',
      '新生北路一段',
      '新生北路三段',
      '新生北路二段',
      '明水路',
      '朱崙街',
      '松江路',
      '林森北路',
      '植福路',
      '樂群三路',
      '樂群二路',
      '民族東路',
      '民族西路',
      '民權東路一段',
      '民權東路三段',
      '民權東路二段',
      '民權西路',
      '民生東路一段',
      '民生東路三段',
      '民生東路二段',
      '民生西路',
      '渭水路',
      '濱江街',
      '玉門街',
      '興安街',
      '華陰街',
      '農安街',
      '通北街',
      '遼寧街',
      '錦州街',
      '錦西街',
      '長安東路一段',
      '長安東路二段',
      '長安西路',
      '長春路',
      '雙城街',
      '龍江路'
    ]

    const filterOptions = computed(() => {
      return options.filter(option =>
        option.toLowerCase().includes(selectedValue.value.toLowerCase())
      )
    })
    return {
      selectedValue,
      options,
      filterOptions
    }
  }
})
</script>

<style></style>
