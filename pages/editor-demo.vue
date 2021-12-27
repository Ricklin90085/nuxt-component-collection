<template>
  <div class="container mx-auto pt-5">
    <Editor ref="editorRef" />
    <button
      class="px-3 py-2 mt-3 text-white bg-indigo-500 rounded-md hover:bg-indigo-600 focus:ring-4 focus:ring-indigo-600/40"
      @click="getEditorContent"
    >
      輸出資料
    </button>
    <div v-if="json" class="export mt-3">
      <pre><code class="block px-3 py-2 text-sm text-gray-500 bg-gray-100 whitespace-pre-wrap rounded-md" v-html="json" /></pre>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const editorRef = ref(null)
    const json = ref(null)
    const getEditorContent = () => {
      json.value = editorRef.value.getContent()
    }

    return {
      editorRef,
      getEditorContent,
      json
    }
  }
})
</script>
