<template>
  <view class="page-wrap">
    <u-navbar title="" placeholder left-icon="" right-icon="camera-fill" />
    <view class="flex items-center bg-white pb-30rpx pl-30rpx pr-20rpx">
      <view class="mr-40rpx">
        <u-avatar src="/static/images/logo.png" size="90" />
      </view>
      <view class="flex-1">
        <view class="pb-10rpx font-size-36rpx">
          微信用户
        </view>
        <view class="u-tips-color font-size-28rpx">
          微信号:uni-app
        </view>
      </view>
      <view class="ml-10rpx p-10rpx">
        <u-icon name="scan" color="#969799" />
      </view>
      <view class="ml-10rpx p-10rpx">
        <u-icon name="arrow-right" color="#969799" />
      </view>
    </view>
  </view>
</template>
<script setup lang="ts">
  import {ref} from 'vue'
  const isLogin = ref<boolen>(false)
</script>
