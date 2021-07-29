<template>
  <button
    :class="{
      'bg-black': isActive ? isActive() : null,
      'text-white': isActive ? isActive() : null
    }"
    class="c-editor-menu-item inline-block w-7 h-7 p-1 mr-1 rounded hover:bg-black hover:text-white"
    :title="title"
    @click="action"
  >
    <div v-html="require(`@/assets/img/icon/remixicon/${icon}.svg?raw`)" />
  </button>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  props: {
    icon: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    action: {
      type: Function,
      required: true
    },
    isActive: {
      type: Function,
      default: null
    }
  },
  setup () {}
})
</script>

<style lang="scss">
.c-editor-menu-item {
  svg {
    width: 100%;
    height: 100%;
    fill: currentColor;
  }
}
</style>
