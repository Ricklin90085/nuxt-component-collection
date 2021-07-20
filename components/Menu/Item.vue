<template>
  <div class="cursor-pointer" @click="handleClick">
    <slot />
  </div>
</template>

<script>
import { defineComponent, inject } from '@vue/composition-api'

export default defineComponent({
  setup () {
    const api = inject('MenuContext')

    const handleClick = () => {
      api.closeMenu()
    }

    return {
      handleClick
    }
  }
})
</script>

<style></style>
