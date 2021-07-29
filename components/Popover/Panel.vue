<template>
  <transition
    enter-active-class="transition duration-150 ease-out"
    enter-class="translate-y-1 opacity-0"
    enter-to-class="translate-y-0 opacity-100"
    leave-active-class="transition duration-150 ease-in"
    leave-class="translate-y-0 opacity-100"
    leave-to-class="translate-y-1 opacity-0"
  >
    <div v-if="api.popoverState">
      <slot />
    </div>
  </transition>
</template>

<script>
import { defineComponent, inject } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const api = inject('PopoverContext')
    return {
      api
    }
  }
})
</script>

<style></style>
