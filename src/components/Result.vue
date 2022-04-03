<script setup>
import { useVirtualList } from "@vueuse/core";
import { computed } from "vue";

const props = defineProps(["result", "running"]);
const resultList = computed(() => props.result)
const { list, containerProps, wrapperProps } = useVirtualList(resultList, {
  // Keep `itemHeight` in sync with the item's row.
  itemHeight: 41,
  overscan: 40
});
</script>

<template>
  <div class="card">
    <h6 class="card-header">📋 结果</h6>
    <div v-bind="containerProps" class="card-body">
      <ul v-bind="wrapperProps" class="list-group" v-if="!running">
        <li
          class="list-group-item"
          v-for="{ index, data } in list"
          :key="index"
        >
          {{ data }}
        </li>
      </ul>
      <div
        style="height: 12.5rem"
        class="container row m-0 align-items-center justify-content-center"
        v-else
      >
        <div class="spinner-border text-primary mt-5" role="status"></div>
        <span class="text-center mb-5">计算中...</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-body {
  max-height: 14.5rem;
  overflow: auto;
}
</style>
