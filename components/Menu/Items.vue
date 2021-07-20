<template>
  <transition
    enter-active-class="transition duration-1200 ease-out"
    enter-class="translate-y-1 opacity-0"
    enter-to-class="translate-y-0 opacity-100"
    leave-active-class="transition duration-150 ease-in"
    leave-class="translate-y-0 opacity-100"
    leave-to-class="translate-y-1 opacity-0"
  >
    <div v-if="visible" ref="itemsRef">
      <slot />
    </div>
  </transition>
</template>

<script>
import { computed, defineComponent, inject, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup () {
    const itemsRef = ref(null)
    const api = inject('MenuContext')
    const visible = computed(() => {
      return api.menuState
    })

    return {
      visible,
      itemsRef
    }
  }
})
</script>

<style></style>
