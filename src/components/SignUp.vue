<template>
  <el-form class="max-w-[360px] w-full" :model="state.form">
    <el-form-item class="">
      <label class="text-neutral-800 leading-5 font-medium mb-2">Email</label>
      <el-input placeholder="trana@gmail.com" clearable v-model="state.form.email" />
    </el-form-item>
    <el-form-item>
      <label class="text-neutral-800 leading-5 font-medium mb-2">Password</label>
      <el-input
        placeholder="Password"
        type="password"
        show-password
        v-model="state.form.password"
      />
    </el-form-item>
    <el-form-item>
      <label class="text-neutral-800 leading-5 font-medium mb-2">Confirm Password</label>
      <el-input
        placeholder="Confirm Password"
        type="password"
        show-password
        v-model="state.form.confirmPassword"
      />
    </el-form-item>
    <el-button class="w-full bg-sign text-white rounded-lg h-11 mt-3">Sign up</el-button>
    <el-button class="w-full rounded-lg h-11 mt-4 !ml-0">
      <img src="../assets/image/Google_icon.svg" alt="gogle-icon" class="mr-2" />
      Sign in with Google
    </el-button>
    <p class="mt-5 text-center text-sm">
      Already have an account?
      <el-button type="primary" link @click="emit('convert-sign-in', true)"> Sign in </el-button>
    </p>
  </el-form>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const emit = defineEmits(['convert-sign-in'])
const state = reactive({
  form: {
    password: '',
    confirmPassword: '',
    email: '',
    checked: false
  }
})
</script>

<style>
.bg-sign {
  background-color: #5429ff;
}
</style>
