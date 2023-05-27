<template>
  <!-- <main class="container-xl h-screen flex justify-center items-center bg-zinc-100"> -->
  <div class="w-full flex justify-center items-center bg-zinc-100">
    <el-container class="max-w-[1200px] w-full">
      <el-main>
        <el-card class="w-full h-full rounded-[4%]">
          <el-row class="block md:flex">
            <el-col :span="12" :md="10" :xs="24" class="w-full">
              <div class="pl-5">
                <img src="./assets/image/Logo.svg" alt="" class="hidden md:block" />
                <img src="./assets/image/Logo_mobile.svg" alt="" class="m-auto md:hidden" />
              </div>
              <div
                class="max-w-[360px] w-full flex flex-col justify-center items-center h-full mx-auto mt-6 md:mt-0"
              >
                <div class="w-full res-mt mb-6 md:mb-14">
                  <h1
                    style="color: #344054"
                    class="font-bold text-[32px] md:text-[40px] leading-10 mb-2"
                  >
                    NFT Access
                  </h1>
                  <p class="text-sm md:text-base" style="color: #667085">
                    Please fill your detail to access your account.
                  </p>
                </div>
                <SignIn v-if="state.convertForm" @convert-sign-in="handleAuth" />
                <SignUp v-else @convert-sign-in="handleAuth" />
              </div>
            </el-col>
            <el-col :span="12" :md="14" class="hidden md:block">
              <img src="./assets/image/bg_01.png" alt="" />
            </el-col>
          </el-row>
        </el-card>
      </el-main>
    </el-container>
  </div>
  <!-- </main> -->
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import SignIn from './components/SignIn.vue'
import SignUp from './components/SignUp.vue'

const state = reactive({
  convertForm: true
})

const handleAuth = (val: boolean) => {
  state.convertForm = val
}
</script>

<style>
@media screen and (min-width: 768px) and(max-width: 991px) {
  .res-mt {
    margin-bottom: 1rem;
  }
  .el-card__body {
    padding-left: 0px;
  }
}

@media screen and (min-width: 992px) {
  .res-mt {
    margin-bottom: 3.5rem;
  }
}
</style>
