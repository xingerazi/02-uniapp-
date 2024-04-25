<script setup lang="ts">
import type { HotItem } from '@/types/home'

// 定义 props 接收数据
defineProps<{
  list: HotItem[]
}>()
</script>

<template>
  <!-- 推荐专区 -->
  <view class="panel hot">
    <view class="item">
      <view class="title">
        <text class="title-text">体育+旅游</text>
        <text class="title-desc">路线推荐</text>
      </view>
      <navigator hover-class="none" url="/pages/index/index" class="cards">
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
      </navigator>
    </view>
    <view class="item">
      <view class="title">
        <text class="title-text">体育+旅游</text>
        <text class="title-desc">路线推荐</text>
      </view>
      <navigator hover-class="none" url="/pages/index/index" class="cards">
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
      </navigator>
    </view>
    <view class="item">
      <view class="title">
        <text class="title-text">体育+旅游</text>
        <text class="title-desc">路线推荐</text>
      </view>
      <navigator hover-class="none" url="/pages/index/index" class="cards">
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
      </navigator>
    </view>
    <view class="item">
      <view class="title">
        <text class="title-text">体育+旅游</text>
        <text class="title-desc">路线推荐</text>
      </view>
      <navigator hover-class="none" url="/pages/index/index" class="cards">
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
        <image class="image" mode="aspectFit" src="../../../static/journey/avatar.jpg"></image>
      </navigator>
    </view>
  </view>
</template>

<style lang="scss">
@import '../styles/hot.scss';
</style>
