<template>
  <div class="horizontal-list">
    <div class="cell-wrapper" v-for="index in source.count" :key="index">
      <div class="cell">
        {{ Math.floor(Math.random() * 100) }}
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue'

interface SourceInterface {
  count: number;
}

defineProps<{ source: SourceInterface }>()
</script>

<style scoped lang="scss">
.horizontal-list {
  display: flex;
}

.cell {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  border: 1px solid lightcoral;
  border-radius: 8px;
  transition: transform 0.3s ease;

  &-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    margin: 5px;

    &:hover {
      .cell {
        transform: scale(0.8);
        cursor: pointer;
      }
    }
  }
}
</style>
