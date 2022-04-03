<script setup>

const props = defineProps(['result', 'running'])

</script>

<template>
  <div class="card">
    <h6 class="card-header">📋 结果</h6>
    <div class="card-body">
      <ul class="list-group" v-if="!running">
        <li class="list-group-item" v-for="(item, index) in props.result" :key="index">{{ item }}</li>
      </ul>
      <div
        style="height: 12.5rem;"
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