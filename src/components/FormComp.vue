<template>
  <div>
    <el-form :inline="true" :model="form" class="demo-form-inline">
      <slot />
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Query</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const form = ref({})

const onSubmit = () => {
}
</script>
