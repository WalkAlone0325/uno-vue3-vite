<script setup lang="ts">
defineProps<{
  type: string
  label: string
}>()
const val = defineModel()

</script>

<template>
  <el-form-item :label="label">
    <el-input :type="type" v-model="val"></el-input>
  </el-form-item>
</template>
