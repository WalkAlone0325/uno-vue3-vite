<template>
  <el-form :inline="true" :model="formInline" class="demo-form-inline">
    <slot />
    <el-form-item>
      <el-button type="primary" @click="onSubmit">Query</el-button>
    </el-form-item>
  </el-form>
</template>

<script lang="ts" setup>
import { ref, useSlots } from 'vue'

const slots = useSlots()
const formInline = ref({})

const onSubmit = () => {
  const vals = slots.default!().map(slot => slot.props!.modelValue)
  console.log(vals)


  console.log(slots.default!(), 'submit!')
}
</script>

<style>
.demo-form-inline .el-input {
  --el-input-width: 220px;
}

.demo-form-inline .el-select {
  --el-select-width: 220px;
}
</style>
