<template>
  <div>
    <FormComp>
      <FormItem v-for="i in data" :key="i.id" v-model="i.value" :label="i.label" :type="i.type" />
    </FormComp>

    <el-button @click="getData">获取数据</el-button>
  </div>
</template>

<script lang="ts" setup>
import FormComp from '@/components/FormComp.vue'
import FormItem from '@/components/FormItem.vue'
import { ref } from 'vue'

const data = ref([
  {
    id: 1,
    label: 'label1',
    value: 'val1',
    type: 'text'
  },
  {
    id: 2,
    label: 'label2',
    value: 'val2',
    type: 'text'
  }
])

const getData = () => {
  console.log(data)
}



</script>
