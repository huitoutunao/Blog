<template>
  <div class="page">
    <my-input ref="myInputRef" v-model="input" placeholder="请输入">
      <template #prefix>
        <el-icon class="el-input__icon"><search /></el-icon>
      </template>
      <template #suffix>
        <el-icon class="el-input__icon"><calendar /></el-icon>
      </template>
    </my-input>
  </div>
</template>

<script setup>
import { nextTick, onMounted, ref } from 'vue'
import { Calendar, Search } from '@element-plus/icons-vue'
import MyInput from '@/components/MyInput.vue'

const input = ref('')
const myInputRef = ref()

onMounted(() => {
  nextTick(() => {
    myInputRef.value.inputRef.focus()
  })
})
</script>

<style lang="scss" scoped>
.page {
  padding: 30px;
}
</style>
