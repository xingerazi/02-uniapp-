<script setup lang="ts">
import { getHomeGoodsGuessLikeAPI } from '@/services/home'
import type { PageParams } from '@/types/global'
import type { GuessItem } from '@/types/home'
import { onMounted, ref } from 'vue'

// 分页参数
const pageParams: Required<PageParams> = {
  page: 1,
  pageSize: 10,
}
// 猜你喜欢的列表
const guessList = ref<GuessItem[]>([
  {
    id: '1',
    name: '居家旅行常备家用医疗包（含医疗用品）',
    desc: '装备齐全，我的随行医护师',
    price: '59.00',
    picture: 'https://yanxuan-item.nosdn.127.net/4aec56f5a1af7c3538e47acf301ad15b.png',
    orderNum: 8126,
  },
  {
    id: '2',
    name: '还原猫咪排泄天性，进口膨润土砂6千克',
    desc: '进口矿砂，强力除臭凝结',
    price: '59.00',
    picture: 'https://yanxuan-item.nosdn.127.net/4c271a733bb1461d39162c0d807b1b02.png',
    orderNum: 5961,
  },
  {
    id: '3',
    name: '三分钟即享简餐，日式即食咖喱150克',
    desc: '日式风味，甘香醇厚',
    price: '15.00',
    picture: 'https://yanxuan-item.nosdn.127.net/3a3d282779030c70e67dc0825ede50d3.png',
    orderNum: 3283,
  },
  {
    id: '4',
    name: '地道卤香好味道，桂林鲜米粉245克*6盒',
    desc: '无人工添加防腐剂，鲜嫩爽滑',
    price: '69.00',
    picture: 'https://yanxuan-item.nosdn.127.net/26d71d6eb4c00ed727ad9f54ae4ce553.png',
    orderNum: 3410,
  },
  {
    id: '5',
    name: '【囤货装】日本橙油精华去油污泡沫3瓶装',
    desc: '强力除油污，萃取橙油精华',
    price: '67.50',
    picture: 'https://yanxuan-item.nosdn.127.net/188e05584a056b0e2f17e8c568da8c00.png',
    orderNum: 3120,
  },
  {
    id: '6',
    name: '艾灸理疗随时随地，灸疗装置8头/12头',
    desc: '哪里不适灸哪里，全身都可灸',
    price: '99.00',
    picture: 'https://yanxuan-item.nosdn.127.net/941abaee58a88cb104228fe2c4cfdeb1.png',
    orderNum: 5785,
  },
  {
    id: '7',
    name: '经典格子元素，男童加绒格子衬衫',
    desc: '经典格子元素，翻盖小贴袋装饰',
    price: '125.00',
    picture: 'https://yanxuan-item.nosdn.127.net/084f82c43a71bbc4d280fbb09a47a028.jpg',
    orderNum: 11261,
  },
  {
    id: '8',
    name: '快速吸水防回渗，宠物训导垫S码80片/袋',
    desc: '漏斗般吸水，一垫多用更省心',
    price: '35.80',
    picture: 'https://yanxuan-item.nosdn.127.net/17f5a18b4125733023cad09d6b7852db.jpg',
    orderNum: 1888,
  },
  {
    id: '9',
    name: '德国莫泽尔传统版雷司令干白2019750ml',
    desc: '来自摩泽尔传奇名庄',
    price: '138.00',
    picture: 'https://yanxuan-item.nosdn.127.net/bcb8efeee3977d417b961c1eba4584a5.jpg',
    orderNum: 5694,
  },
  {
    id: '10',
    name: '暖腰暖腹暖胃，蕲艾暖宫腰带',
    desc: '暖宫暖腰暖胃，大面积热敷≈3片暖宝宝',
    price: '49.00',
    picture: 'https://yanxuan-item.nosdn.127.net/9892cc73945da1591fa5259ad076b23c.jpg',
    orderNum: 9781,
  },
])
// 已结束标记
// const finish = ref(false)
// // 获取猜你喜欢数据
// const getHomeGoodsGuessLikeData = async () => {
//   // 退出分页判断
//   if (finish.value === true) {
//     return uni.showToast({ icon: 'none', title: '没有更多数据~' })
//   }
//   const res = await getHomeGoodsGuessLikeAPI(pageParams)
//   // guessList.value = res.result.items
//   // 数组追加
//   guessList.value.push(...res.result.items)
//   // 分页条件
//   if (pageParams.page < res.result.pages) {
//     // 页码累加
//     pageParams.page++
//   } else {
//     finish.value = true
//   }
// }
// 重置数据
// const resetData = () => {
//   pageParams.page = 1
//   guessList.value = []
//   finish.value = false
// }
// 组件挂载完毕
// onMounted(() => {
//   getHomeGoodsGuessLikeData()
// })
// 暴露方法
// defineExpose({
//   resetData,
//   getMore: getHomeGoodsGuessLikeData,
// })
</script>

<template>
  <!-- 猜你喜欢 -->
  <view class="caption">
    <text class="text">猜你喜欢</text>
  </view>
  <view class="guess">
    <navigator
      class="guess-item"
      v-for="item in guessList"
      :key="item.id"
      url="/pages/goods/goods?id=3986121"
    >
      <image class="image" mode="aspectFill" :src="item.picture"></image>
      <view class="name">{{ item.name }}</view>
      <view class="price">
        <text class="small">¥</text>
        <text>{{ item.price }}</text>
      </view>
    </navigator>
  </view>
  <view class="loading-text"> 没有更多数据~ </view>
</template>

<style lang="scss">
:host {
  display: block;
}
/* 分类标题 */
.caption {
  display: flex;
  justify-content: center;
  line-height: 1;
  padding: 36rpx 0 40rpx;
  font-size: 32rpx;
  color: #262626;
  .text {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 28rpx 0 30rpx;

    &::before,
    &::after {
      content: '';
      width: 20rpx;
      height: 20rpx;
      background-image: url(@/static/images/bubble.png);
      background-size: contain;
      margin: 0 10rpx;
    }
  }
}

/* 猜你喜欢 */
.guess {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0 20rpx;
  .guess-item {
    width: 345rpx;
    padding: 24rpx 20rpx 20rpx;
    margin-bottom: 20rpx;
    border-radius: 10rpx;
    overflow: hidden;
    background-color: #fff;
  }
  .image {
    width: 304rpx;
    height: 304rpx;
  }
  .name {
    height: 75rpx;
    margin: 10rpx 0;
    font-size: 26rpx;
    color: #262626;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }
  .price {
    line-height: 1;
    padding-top: 4rpx;
    color: #cf4444;
    font-size: 26rpx;
  }
  .small {
    font-size: 80%;
  }
}
// 加载提示文字
.loading-text {
  text-align: center;
  font-size: 28rpx;
  color: #666;
  padding: 20rpx 0;
}
</style>
