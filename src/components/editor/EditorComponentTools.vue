<!-- eslint-disable vue/no-extra-parens ломает подсевку синтаксиса -->
<template>
  <div class="tools">
    <template
      v-for="i in tools"
      :key="i.id"
    >
      <InputTool
        v-if="i.type === 'input' || i.type === 'inputNumber'"
        :id="i.id"
        :key="i.id"
        :title="i.label"
        :type="i.type === 'input' ? 'string' : 'number'"
        :value="i.value as string"
      />
      <PaddingTool
        v-if="i.type === 'padding'"
        :id="i.id"
        :value="i.value"
        :title="i.label"
      />
      <SpacingTool
        v-if="i.type === 'spacing'"
        :id="i.id"
        :value="i.value"
        :title="i.label"
      />
      <ColorPickerTool
        v-if="i.type === 'colorPicker'"
        :id="i.id"
        v-model:value="i.value"
        :title="i.label"
      />
      <ToggleTool
        v-if="i.type === 'toggle'"
        :id="i.id"
        :title="i.label"
        :value="i.value"
      />
      <ImageTool
        v-if="i.type === 'image'"
        :id="i.id"
        :title="i.label"
        :value="i.value"
      />
      <BackgroundImageTool
        v-if="i.type === 'bgImage'"
        :id="i.id"
        :title="i.label"
        :value="i.value"
      />
      <AlignTool
        v-if="i.type === 'align'"
        :id="i.id"
        :value="i.value"
        :title="i.label"
      />
      <TextEditorTool
        v-if="i.type === 'textEditor'"
        :id="i.id"
        :value="i.value"
        :title="i.label"
      />
      <MultiTool
        v-if="i.type === 'multi'"
        :id="i.id"
        :value="i.value"
        :title="i.label"
      />
    </template>
  </div>
</template>

<script setup lang="ts">
import { provide } from 'vue'

import type { Tool } from '@/types/editor'

interface Props {
  tools: Tool[]
  parentMultiToolId?: string
}

const props = defineProps<Props>()

provide('parentMultiToolId', props.parentMultiToolId)
</script>

<style lang="scss" scoped></style>
