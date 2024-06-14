<template>
  <view class="card">
     <view class="text-content">
       <text class="tag">{{ title2 }}</text>
       <text class="title">{{ title1 }}</text>
       <text class="info">{{ title3 }}</text>
       <view class="btn" @tap="goTo">前往</view>
     </view>
     <view class="image-box">
       <image
        class="pic"
        :src="imgUrl"
         mode="scaleToFill"
       />
     </view>
  </view>
</template>

<script setup lang="ts">
  const {title1,title2,title3,link,imgUrl} = defineProps<{
      title1:string
      title2?:string
      title3?:string
      imgUrl:string
      link:string
    }>()
const goTo=()=>{
  uni.navigateTo({url:link})
}
</script>
<style lang="scss" scoped>
.card{
  border-radius: 40rpx;
  display: flex;
  align-items: center;
  background: #fff;
  padding:38rpx;
  .text-content{
    text{
      display: block;
    }
    width:50%;
    flex:1;
    display: flex;
    height: 100%;
    flex-direction: column;
    justify-content: space-between;
    row-gap: 30rpx;
    .tag{
       font-size: 28rpx;
       color:rgb(249, 191, 1);
       font-weight: 400;
    }
    .title{
      font-size:32rpx;
      color:#000;
      font-weight: 700;
    }
    .info{
      color: #444;
      font-size: 26rpx;
      font-weight: 500;
    }
    .btn{
      padding:10rpx 24rpx;
      border-radius: 999rpx;
      background: #3baf78;
      color:#fff;
      font-size: 28rpx;
      width:fit-content;
      font-weight: 400;
    }
  }
  .image-box{
    width:50%;
    flex:1;
    display: flex;
    justify-content: center;
    align-items: center;
    .pic{
      width: 240rpx;
      height: 240rpx;
      object-fit: cover;
    }
  }
}
</style>
