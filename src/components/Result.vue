<script setup>

const props = defineProps(['result', 'computing'])

</script>

<template>
  <div class="card">
    <h6 class="card-header">📋 结果</h6>
    <div class="card-body">
      <div class="container row m-0 align-items-center justify-content-center" style="height: 12.5rem;" v-if="props.computing">
        <div class="spinner-border" role="status">
          <span class="visually-hidden">Loading...</span>
        </div>
      </div>
      <ul class="list-group placeholder-glow" v-else-if="props.result.length == 0">
        <li
          class="list-group-item placeholder mb-1"
          v-for="item in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]"
        ></li>
      </ul>
      <ul class="list-group" v-else-if="!props.computing">
        <li class="list-group-item mb-1" v-for="item in props.result">{{ item }}</li>
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