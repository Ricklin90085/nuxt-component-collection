<template>
  <div v-if="editor" class="w-96 border-2 border-black rounded-lg">
    <EditorMenuBar :editor="editor" />
    <editor-content class="editor__content px-4 py-5" :editor="editor" />
  </div>
</template>

<script>
import {
  defineComponent,
  onBeforeUnmount,
  onMounted,
  ref
} from '@nuxtjs/composition-api'
import { Editor, EditorContent } from '@tiptap/vue-2'
import StarterKit from '@tiptap/starter-kit'

export default defineComponent({
  components: {
    EditorContent
  },
  setup() {
    const editor = ref(null)
    const getContent = () => {
      return editor.value.getJSON()
    }
    onMounted(() => {
      editor.value = new Editor({
        content: '<p>I’m running tiptap with Nuxt.js. 🎉</p>',
        extensions: [StarterKit]
      })
    })
    onBeforeUnmount(() => {
      editor.value.destroy()
    })

    return {
      editor,
      getContent
    }
  }
})
</script>

<style lang="scss">
.ProseMirror {
  @apply focus-visible:outline-none;
}
.editor__content {
  ul {
    @apply px-4 list-disc;
  }
  ol {
    @apply px-4 list-decimal;
  }
}
</style>
