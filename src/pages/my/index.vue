<script setup lang="ts">
definePage({
  name: 'my',
  layout: 'tabbar',
  style: {
    navigationBarTitleText: '我的',
  },
})

const router = useRouter()

// 静态占位资料，后续接入用户体系时替换为 store/接口数据
const profile = {
  avatar: 'https://wot-ui.cn/favicon.svg',
  nickname: '熊计划用户',
  bio: 'ID：bear_0001',
}

// 个人中心常用菜单，key 用 index 与书写规范一致
const menus = [
  { title: '我的资料', icon: 'user' },
  { title: '我的消息', icon: 'message' },
  { title: '我的收藏', icon: 'star' },
  { title: '关于我们', icon: 'info' },
]

// 订单快捷入口，按常见电商个人中心布局：图标在上、文字在下
const orders = [
  { title: '待付款', icon: 'tag' },
  { title: '待售后', icon: 'refresh' },
  { title: '待评价', icon: 'star' },
  { title: '全部订单', icon: 'ordered-list' },
]

const { show: showToast } = useGlobalToast()

function handleMenuTap(title: string, routeName?: string) {
  if (routeName) {
    router.push({ name: routeName })
    return
  }
  showToast(`${title} 敬请期待`)
}
</script>

<template>
  <view class="min-h-screen py-3">
    <!-- 资料卡片：头像 + 昵称 -->
    <view class="mx-3 mb-3 flex items-center gap-4 rounded-3 px-4 py-6 wot-bg-filled-oppo">
      <wd-img
        :src="profile.avatar"
        mode="aspectFill"
        custom-class="h-16 w-16 rounded-full"
      />
      <view class="flex flex-1 flex-col gap-1">
        <text class="text-5 font-bold wot-text-text-main">
          {{ profile.nickname }}
        </text>
        <text class="text-3 wot-text-text-secondary">
          {{ profile.bio }}
        </text>
      </view>
    </view>

    <!-- 我的订单快捷入口 -->
    <demo-block title="我的订单" transparent>
      <view class="grid grid-cols-4 mx-3 rounded-2 py-4 wot-bg-filled-oppo">
        <view
          v-for="(item, index) in orders"
          :key="index"
          class="flex flex-col items-center gap-2"
          @click="handleMenuTap(item.title)"
        >
          <wd-icon :name="item.icon" size="26px" class="wot-text-text-main" />
          <text class="text-3 wot-text-text-main">
            {{ item.title }}
          </text>
        </view>
      </view>
    </demo-block>

    <!-- 常用菜单 -->
    <demo-block title="常用功能" transparent>
      <wd-cell-group border custom-class="rounded-2! overflow-hidden">
        <wd-cell
          v-for="(item, index) in menus"
          :key="index"
          :title="item.title"
          :icon="item.icon"
          is-link
          @click="handleMenuTap(item.title, item.title === '我的资料' ? 'my-info' : undefined)"
        />
      </wd-cell-group>
    </demo-block>
  </view>
</template>
