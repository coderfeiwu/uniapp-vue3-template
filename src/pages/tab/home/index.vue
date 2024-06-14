<template>
  <view class="container">
    <view class="main-wrapper">
      <up-search v-model="keyword" placeholder="请输入关键词" :showAction="false"></up-search>
      <view class="tab">
        <up-tabs  lineWidth="30"
          lineColor="#98F5FF"
          :activeStyle="{
              color: 'skybule',
              fontWeight: 'bold',
          }"
          :inactiveStyle="{
              color: '#606266',
              transform: 'scale(1)'
          }" :list="list1" @click="click"></up-tabs>
      </view>
      </view>
      <view class="choose-container">
         <scroll-view scroll-y="true" :style="{'height':contentHeight + 'px'}" class="left-tab">
            <view @click="changeSlider(index)" v-for="(item,index) of sliderTab" :key="index" v-bind:class="{'active' :sliderIndex === index,'slider-item':true, }">
               <text class="item-text">
                 {{ item.name }}
               </text>
            </view>
         </scroll-view>
         <scroll-view scroll-y="true"  :style="{'height':contentHeight + 'px'}" class="slider-content">
            <view id="target1">
              <view class="title-box">
                <view class="dot"></view>
                <text class="title">常见茅台</text>
              </view>
              <text class="time">2024.6.12</text>
              <view class="product-item" v-for="(item,index) in 40">
                  <text class="product-name">贵州特产盲盒/盒</text>
                  <view class="right-box">
                     <text class="price">¥1999.00</text>
                  </view>
              </view>
            </view>
            <view id="target2">
              <view class="title-box">
                <view class="dot"></view>
                <text class="title">飞天茅台</text>
              </view>
              <text class="time">2024.6.12</text>
              <view class="product-item" v-for="(item,index) in 40">
                  <text class="product-name">贵州特产盲盒/盒</text>
                  <view class="right-box">
                     <text class="price">¥1999.00</text>
                  </view>
              </view>
            </view>
         </scroll-view>
      </view>
  </view>
</template>

<script setup lang="ts">
import {ref,reactive} from 'vue'
import { onReady } from '@dcloudio/uni-app';
  let getWindowInfo = uni.getWindowInfo()
  const activeIndex = ref<number>(0)
  const sliderIndex = ref<number>(0)
  const keyword = ref<string>('')
  const list1 = reactive([
    { name: '美酒' },
    { name: '戴森' },
 ]);
 const sliderTab = reactive([
  {name:"茅台一",value:"mt1"},
  {name:"茅台二",value:"mt2"},
  {name:"茅台三",value:"mt3"},
  {name:"茅台四",value:"mt4"},
  {name:"茅台五",value:"mt5"},
  {name:"茅台二",value:"mt2"},
  {name:"茅台三",value:"mt3"},
  {name:"茅台四",value:"mt4"},
  {name:"茅台五",value:"mt5"},
  {name:"茅台二",value:"mt2"},
  {name:"茅台三",value:"mt3"},
  {name:"茅台四",value:"mt4"},
  {name:"茅台五",value:"mt5"},
  {name:"茅台二",value:"mt2"},
  {name:"茅台三",value:"mt3"},
  {name:"茅台四",value:"mt4"},
  {name:"茅台五",value:"mt5"},
 ])
// 定义方法
function click(item:any) {
  activeIndex.value = item.index
}
onReady(()=>{
  uni.createSelectorQuery().select(".choose-container").boundingClientRect((data:any) => {
    contentHeight.value = getWindowInfo.windowHeight - data.top -30;
}).exec();
})
const changeSlider = (index:number)=>{
  sliderIndex.value = index;
  const str = `target${index + 1}`
  uni.createSelectorQuery().select(`#${str}`).boundingClientRect((data:any) => {
    console.log(data.top);
}).exec();

}
const contentHeight = ref<number>(300)

</script>
<style lang="scss" scoped>
.container{
  display: flex;
  flex-direction: column;
  width: 100%;
  height:100%;
  min-height:100vh;
  .main-wrapper{
    padding:0 30px;
    .tab{
      margin-top:40rpx;
      display: flex;
      column-gap:40rpx;
      .tab-item{
        font-size: 36rpx;
        color:#333;
      }
    }
 }
 .choose-container{
    background: #f7f7f7;
    padding-top:60rpx;
    height: 100%;
    width: 100%;
    display: flex;
    column-gap: 32rpx;
    align-items: start;
    flex:1;
    .left-tab{
      background: #efefef;
      height: 100%;
      width: 220rpx;
      display: flex;
      flex-direction: column;
      .slider-item{
        width: 100%;
        height: 92rpx;
        display: flex;
        justify-content: center;
        transition:all 0.2s;
        align-items: center;
        border-right:18rpx solid transparent;
        &.active{
          border-right:18rpx solid #40929b;
          color: #40929b;
          background: linear-gradient(to right, #c4e4e7, transparent);;

        }
        .item-text{
           font-size:38rpx;
        }
      }
    }
    .slider-content{
      flex:1;
      .title-box{
        display: flex;
        margin-bottom:28rpx;
        align-items: center;
        .dot{
          width: 16rpx;
          height: 16rpx;
          margin-right: 20rpx;
          border-radius: 50%;
          background:#40929b;
        }
        .title{
           font-size: 38rpx;
           margin-top:30rpx;
         }
         &:first-of-type{
          .title-box{
            .title{
              margin:0px;
            }
          }
         }
      }
      .time{
        font-size: 28rpx;
        color:#444;
      }
      .product-item{
        display: flex;
        flex-direction: row;
        align-items: center;
        padding:0 18rpx;
        height: 91rpx;
        border-bottom:1px solid #efefef;
        justify-content: space-between;
        .product-name{
          width: 55%;
          font-size: 24rpx;
          color:#444;
        }
        .right-box{
          width: 45%;
          display: flex;
          align-items: center;
        }
      }
    }
 }
}
</style>
