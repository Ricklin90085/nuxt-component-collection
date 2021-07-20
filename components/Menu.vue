<template>
  <div>
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

export default defineComponent({
  setup () {
    const menuState = ref(false)
    const menuRef = ref(null)
    const api = reactive({
      menuState,
      openMenu: () => {
        menuState.value = true
      },
      closeMenu: () => {
        menuState.value = false
      }
    })

    provide('MenuContext', api)
    return {
      api,
      menuRef
    }
  }
})
</script>

<style></style>
