<script setup lang="ts">
import type { CategoryItem } from '@/types/home'

// 定义 props 接收数据
defineProps<{
  list: CategoryItem[]
}>()
</script>

<template>
  <view class="category">
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab1.png"></image>
      <text class="text">体育旅游</text>
    </navigator>
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab2.png"></image>
      <text class="text">民族特色</text>
    </navigator>
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab3.png"></image>
      <text class="text">乡村之行</text>
    </navigator>
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab4.png"></image>
      <text class="text">户外探索</text>
    </navigator>
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab5.png"></image>
      <text class="text">冰雪之旅</text>
    </navigator>
    <navigator class="category-item" hover-class="none" url="/pages/index/index">
      <image class="icon" src="../../../static/journey/tab6.png"></image>
      <text class="text">滨海之旅</text>
    </navigator>
  </view>
</template>

<style lang="scss">
@import '../styles/category.scss';
</style>
