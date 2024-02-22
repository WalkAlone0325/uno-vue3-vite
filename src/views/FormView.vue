<template>
  <FormComp>
    <FormItem v-model="formInline.val1"></FormItem>
    <FormItem v-model="formInline.val2"></FormItem>
  </FormComp>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import FormComp from '@/components/FormComp.vue'
import FormItem from '@/components/FormItem.vue'

const formInline = ref({
  val1: '',
  val2: '',
})

</script>
