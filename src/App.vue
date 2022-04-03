<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { ref, computed } from 'vue'
import Parameters from './components/Parameters.vue'
import Result from './components/Result.vue'
import { useWebWorkerFn } from '@vueuse/core'


const { workerFn: compute, workerStatus: computeStatus } = useWebWorkerFn(parameters => {
  let result = []
  let { x, count, firstCondition, firstAction, firstOperator, secondCondition, secondAction, secondOperator } = JSON.parse(parameters)
  switch (firstOperator) {
    case "addition":
      switch (secondOperator) {
        case "addition":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.add(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.add(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "subtract":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.add(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "multiplication":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.add(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "division":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.add(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
      }
      break
    case "subtract":
      switch (secondOperator) {
        case "addition":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.add(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "subtract":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "multiplication":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "division":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
      }
      break
    case "multiplication":
      switch (secondOperator) {
        case "addition":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.add(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "subtract":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "multiplication":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "division":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
      }
      break
    case "division":
      switch (secondOperator) {
        case "addition":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.add(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "subtract":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.subtract(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "multiplication":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.multiply(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
        case "division":
          for (let i = 1; i <= count; i++) {
            if (x != firstCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(firstAction))
            } else if (x == secondCondition) {
              x = math.divide(math.bignumber(x), math.bignumber(secondAction))
            }
            result.push(`第${i}次: x = ${math.format(x)}`)
            console.log(`第${i}次: x = ${math.format(x)}`)
          }
          break
      }
      break
  }
  result.reverse()
  return result
}, { dependencies: [ 'https://cdn.jsdelivr.net/npm/mathjs@10.4.2/lib/browser/math.min.js' ] })

const result = ref([])
const running = computed(() => computeStatus.value === "RUNNING")
const handleCompute = async parameters => {
  result.value = []
  result.value = await compute(JSON.stringify(parameters))
}

</script>

<template>
  <main class="container py-5">
    <header class="container">
      <h1 class="display-6">Compute Program</h1>
      <small class="text-muted">
        一个计算程序，使用
        <mark>For</mark> 语句和
        <mark>If</mark> 语句实现。
      </small>
    </header>
    <main class="my-5 container">
      <div class="row">
        <div class="col-md-7 my-3">
          <Parameters :running="running" @compute="handleCompute" />
        </div>
        <div class="col-md-5 my-3">
          <Result :running="running" :result="result" />
        </div>
      </div>
    </main>
    <footer class="py-3">
      <p class="text-center text-muted mb-0">MIT Licensed | Made by Zhou Haixian</p>
      <p class="text-center text-muted">
        <a href="https://github.com/zhouhaixian/ComputeProgram" target="_blank">Github</a>
      </p>
    </footer>
  </main>
</template>
