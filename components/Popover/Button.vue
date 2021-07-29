<template>
  <div class="cursor-pointer" @click="handleClick">
    <slot />
  </div>
</template>

<script>
import { defineComponent, inject } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const api = inject('PopoverContext')

    const handleClick = () => {
      if (api.popoverState) {
        api.closePopover()
      } else {
        api.openPopover()
      }
    }
    return {
      handleClick
    }
  }
})
</script>

<style></style>
