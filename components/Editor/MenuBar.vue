<template>
  <div class="flex items-center p-1 border-b-2 border-black">
    <template v-for="(item, index) in items">
      <div
        v-if="item.type === 'divider'"
        :key="index"
        class="w-[2px] h-5 ml-2 mr-3 bg-gray-200"
      />
      <EditorMenuItem v-else :key="item.title" v-bind="item" />
    </template>
  </div>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  props: {
    editor: {
      type: Object,
      required: true
    }
  },
  setup (props) {
    const items = [
      {
        icon: 'bold',
        title: 'Bold',
        action: () =>
          props.editor
            .chain()
            .focus()
            .toggleBold()
            .run(),
        isActive: () => props.editor.isActive('bold')
      },
      {
        icon: 'italic',
        title: 'Italic',
        action: () =>
          props.editor
            .chain()
            .focus()
            .toggleItalic()
            .run(),
        isActive: () => props.editor.isActive('italic')
      },
      {
        icon: 'list-unordered',
        title: 'Bullet List',
        action: () =>
          props.editor
            .chain()
            .focus()
            .toggleBulletList()
            .run(),
        isActive: () => props.editor.isActive('bulletList')
      },
      {
        icon: 'list-ordered',
        title: 'Ordered List',
        action: () =>
          props.editor
            .chain()
            .focus()
            .toggleOrderedList()
            .run(),
        isActive: () => props.editor.isActive('orderedList')
      },
      {
        type: 'divider'
      },
      {
        icon: 'arrow-go-back-line',
        title: 'Undo',
        action: () =>
          props.editor
            .chain()
            .focus()
            .undo()
            .run()
      },
      {
        icon: 'arrow-go-forward-line',
        title: 'Redo',
        action: () =>
          props.editor
            .chain()
            .focus()
            .redo()
            .run()
      }
    ]

    return {
      items
    }
  }
})
</script>

<style></style>
