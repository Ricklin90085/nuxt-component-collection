<template>
  <div ref="popoverRef">
    <slot :api="api" />
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
    const popoverRef = ref(null)
    const popoverState = ref(true)
    const api = reactive({
      popoverState,
      openPopover: () => {
        popoverState.value = true
      },
      closePopover: () => {
        popoverState.value = false
      }
    })
    onClickOutside(popoverRef, api.closePopover)
    provide('PopoverContext', api)
    return {
      api,
      popoverRef
    }
  }
})
</script>

<style></style>
