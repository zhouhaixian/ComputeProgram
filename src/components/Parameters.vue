<script setup>
import { onMounted, ref, unref } from 'vue'

const props = defineProps(['running'])
const emit = defineEmits(['compute'])

const parameters = ref({
  x: 625,
  count: 2020,
  firstCondition: 1,
  firstAction: 5,
  firstOperator: 'division',
  secondCondition: 1,
  secondAction: 4,
  secondOperator: 'addition'
})
const reset = () => {
  parameters.value = {
    x: 625,
    count: 2020,
    firstCondition: 1,
    firstAction: 5,
    firstOperator: 'division',
    secondCondition: 1,
    secondAction: 4,
    secondOperator: 'addition'
  }
}
const compute = (event) => {
  emit('compute', unref(parameters))
  event.preventDefault()
}
onMounted(() => {
  compute({ preventDefault: () => null })
})
</script>

<template>
  <div class="card">
    <h6 class="card-header">⚙️ 参数设置</h6>
    <div class="card-body">
      <form action @submit="compute">
        <div class="input-group mb-3">
          <span class="input-group-text">输入 ( x )</span>
          <input class="form-control" type="number" max="999999" step="0.1" v-model="parameters.x" />
          <span class="input-group-text">循环次数</span>
          <input class="form-control" type="number" max="100000" min="1" v-model="parameters.count" />
        </div>
        <div class="input-group mb-3">
          <span class="input-group-text">如果 x ≠</span>
          <input
            class="form-control"
            type="number"
            max="999999"
            step="0.1"
            v-model="parameters.firstCondition"
          />
          <span class="input-group-text">则</span>
          <select class="form-select" v-model="parameters.firstOperator">
            <option value="addition">加上</option>
            <option value="subtract">减去</option>
            <option value="multiplication">乘以</option>
            <option value="division">除以</option>
          </select>
          <input
            class="form-control"
            type="number"
            max="999999"
            step="0.1"
            v-model="parameters.firstAction"
          />
        </div>
        <div class="input-group mb-3">
          <span class="input-group-text">如果 x =</span>
          <input
            class="form-control"
            type="number"
            max="999999"
            step="0.1"
            v-model="parameters.secondCondition"
          />
          <span class="input-group-text">则</span>
          <select class="form-select" v-model="parameters.secondOperator">
            <option value="addition">加上</option>
            <option value="subtract">减去</option>
            <option value="multiplication">乘以</option>
            <option value="division">除以</option>
          </select>
          <input
            class="form-control"
            type="number"
            max="999999"
            step="0.1"
            v-model="parameters.secondAction"
          />
        </div>
        <div class="container">
          <div class="row">
            <input class="btn btn-primary col me-3" type="submit" value="计算" v-if="!running" />
            <button class="btn btn-primary col me-3" type="submit" value="计算" disabled v-else>
              <div class="spinner-border spinner-border-sm" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </button>
            <button class="btn btn-secondary col" type="button" @click="reset">重置</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>
