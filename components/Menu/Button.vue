<template>
  <button @click="handleClick">
    <slot />
  </button>
</template>

<script>
import { defineComponent, inject } from '@vue/composition-api'

export default defineComponent({
  setup () {
    const api = inject('MenuContext')

    const handleClick = () => {
      console.log(api.menuState)
      if (api.menuState) {
        api.closeMenu()
      } else {
        api.openMenu()
      }
    }

    return {
      handleClick
    }
  }
})
</script>

<style></style>
