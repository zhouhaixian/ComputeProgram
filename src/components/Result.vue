<script setup>

const props = defineProps(['result'])

</script>

<template>
  <div class="card">
    <h6 class="card-header">📋 结果</h6>
    <div class="card-body">
      <ul class="list-group">
        <li class="list-group-item" v-for="(item, index) in props.result" :key="index">{{ item }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.card-body {
  max-height: 14.5rem;
  overflow: auto;
}
</style>