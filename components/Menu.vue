<template>
  <div ref="menuRef">
    <slot />
  </div>
</template>

<script>
import {
  defineComponent,
  provide,
  reactive,
  ref
} from '@nuxtjs/composition-api'
import { onClickOutside } from '@vueuse/core'

export default defineComponent({
  setup() {
    const menuRef = ref(null)
    const menuState = ref(true)
    const api = reactive({
      menuState,
      openMenu: () => {
        menuState.value = true
      },
      closeMenu: () => {
        menuState.value = false
      }
    })

    onClickOutside(menuRef, api.closeMenu)

    provide('MenuContext', api)
    return {
      api,
      menuRef
    }
  }
})
</script>

<style></style>
