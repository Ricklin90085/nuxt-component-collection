<template>
  <div>
    <input
      :value="value"
      type="text"
      class="bg-transparent outline-none"
      @focus="handleFocus"
      @input="$emit('input', $event.target.value)"
    >
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
  </div>
</template>

<script>
import { defineComponent, inject } from '@nuxtjs/composition-api'

export default defineComponent({
  model: {
    prop: 'value',
    event: 'input'
  },
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  setup() {
    const api = inject('MenuContext')

    const handleFocus = () => {
      if (api.menuState) {
        api.closeMenu()
      } else {
        api.openMenu()
      }
    }

    return {
      handleFocus
    }
  }
})
</script>

<style></style>
