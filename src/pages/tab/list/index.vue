<template>
  <view class="good-list">
  <view class="top-bar">
      <text class="main-title">选择出货方式</text>
      <text class="subtitle">请选择您的选择出货方式</text>
  </view>
  <view class="mt-24rpx">
    <GoodCard title1="快递报单" title2="寄送" title3="快递信息填写" link="" imgUrl="/static/images/logo.png"></GoodCard>
  </view>
  <view class="mt-24rpx">
    <GoodCard title1="快递报单" title2="寄送" title3="快递信息填写" link="" imgUrl="/static/images/logo.png"></GoodCard>
  </view>
  <view class="mt-24rpx">
    <GoodCard title1="快递报单" title2="寄送" title3="快递信息填写" link="" imgUrl="/static/images/logo.png"></GoodCard>
  </view>

</view>
</template>

<script setup lang="ts">
import GoodCard from '@/components/good-card'
</script>
<style lang="scss" scoped>
.good-list{
   height: 100%;
   min-height: 100vh;
   padding:30rpx 40rpx;
   background: #f7f7f7;
   color:#000;
   .top-bar{
    display: flex;
    flex-direction: column;
    row-gap: 30rpx;
    .main-title{
      font-size: 38rpx;
      color:#222;
      font-weight: 700;
    }
    .subtitle{
      font-size: 28rpx;
      color:#444;
      font-weight: 400;
    }
   }
}
</style>
