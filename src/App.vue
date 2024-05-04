<template>
  <div class="app">
    <VerticalList :count="verticalCount" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import VerticalList from './components/VerticalList.vue'

export default defineComponent({
  name: 'App',
  components: {
    VerticalList
  },
  setup () {
    const verticalCount = ref<number>(Math.floor(Math.random() * 100) + 100)
    return {
      verticalCount
    }
  }
})
</script>

<style>
html, body {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
</style>
