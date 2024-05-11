<template>
  <a-form ref="formRef" :model="formModel">
    <a-form-item label="应用名称" name="name" required>
      <a-input v-model:value="formModel.name" placeholder="请输入应用名称" />
    </a-form-item>
    <a-form-item label="状态" name="status" required>
      <a-switch v-model:checked="formModel.status" />
    </a-form-item>
    <a-form-item label="应用图标" name="icon" required>
      <div class="w-10 h-10 flex items-center justify-center">
        asfklasjflk
      </div>
    </a-form-item>
    <a-form-item label="链接地址" name="link" required>
      <a-input v-model:value="formModel.link" placeholder="请输入链接地址" />
    </a-form-item>
    <a-form-item label="红点提示配置" name="unreadConfig" required>
      <a-radio-group v-model:value="formModel.unreadConfig" :options="options" />
    </a-form-item>
    <a-form-item
      v-if="formModel.unreadConfig !== UNREAD_CONFIG.NONE"
      label="API地址"
      name="unreadApi"
      :required="formModel.unreadConfig === UNREAD_CONFIG.API"
    >
      <div class="flex gap-1">
        <a-input v-model:value="formModel.unreadApi" placeholder="请输入API地址" />
        <a-button type="primary" ghost>
          检测是否可用
        </a-button>
      </div>
    </a-form-item>
  </a-form>
</template>

<script setup>
import { UNREAD_CONFIG } from '@/constants'

const formRef = ref()
const options = [
  { label: 'API', value: 'api' },
  { label: '无', value: 'none' },
]
</script>

<style lang="less" scoped>

</style>
