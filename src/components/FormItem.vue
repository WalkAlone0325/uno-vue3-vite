<script setup lang="ts">

const val = defineModel()
console.log(val)
</script>

<template>
  <el-form-item label="1111">
    <el-input v-model="val"></el-input>
  </el-form-item>
</template>
