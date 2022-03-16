<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { ref } from 'vue'
import Parameters from './components/Parameters.vue'
import Result from './components/Result.vue'

const result = ref([])
const compute = (parameters) => {
  result.value = []
  let { x, count, firstCondition, firstAction, secondCondition, secondAction } = parameters
  for (let i = 1; i <= count; i++) {
    if (x != firstCondition) {
      x *= firstAction
    } else if (x == secondCondition) {
      x += secondAction
    }
    result.value.push(`第${i}次: x = ${x}`)
    console.log(`第${i}次: x = ${x}`)
  }
}

</script>

<template>
  <main class="container py-5">
    <header class="container">
      <h1 class="display-6">计算程序</h1>
      <small class="text-muted">
        一个计算程序，使用
        <mark>For</mark> 语句和
        <mark>If</mark> 语句实现。
      </small>
    </header>
    <main class="my-5 container">
      <div class="row">
        <div class="col-md-7 my-3">
          <Parameters @compute="compute" />
        </div>
        <div class="col-md-5 my-3">
          <Result :result="result" />
        </div>
      </div>
    </main>
  </main>
</template>
