<template>
  <div class="vertical-list">
    <virtual-list style="height: 100vh; overflow-y: auto;"
      :data-key="'id'"
      :data-sources="items"
      :data-component="HorizontalList"
    />

  </div>
</template>

<script setup lang="ts">
import { defineProps, ref } from 'vue'
import HorizontalList from './HorizontalList.vue'
import VirtualList from 'vue3-virtual-scroll-list'

const props = defineProps<{ count: number }>()

const items = ref(
  Array.from({ length: props.count }, (_, index) => ({
    id: index.toString(),
    count: Math.floor(Math.random() * 10) + 10
  }))
)
</script>

<style>
.scroller {
  height: 100%;
}
</style>
