<script setup lang="ts">
definePage({
  name: 'my-info',
  style: {
    navigationBarTitleText: '我的资料',
  },
})

// 静态占位资料，后续接入用户体系时替换为 store/接口数据
const profile = {
  avatar: 'https://wot-ui.cn/favicon.svg',
  nickname: '熊计划用户',
  wechat: 'bear_0001',
  phone: '138****0000',
}

const { show: showToast } = useGlobalToast()

// 各资料项暂为只读展示，点击统一提示占位
function handleItemTap(title: string) {
  showToast(`${title} 编辑功能敬请期待`)
}

// 退出登录当前为模板占位，无真实登录态
function handleLogout() {
  showToast('已退出登录（占位）')
}
</script>

<template>
  <view class="min-h-screen py-3">
    <!-- 头像（独立分组，右侧展示） -->
    <demo-block transparent>
      <wd-cell-group border custom-class="rounded-2! overflow-hidden">
        <wd-cell title="头像" is-link @click="handleItemTap('头像')">
          <wd-img
            :src="profile.avatar"
            mode="aspectFill"
            custom-class="h-10 w-10 rounded-full"
          />
        </wd-cell>
      </wd-cell-group>
    </demo-block>

    <!-- 昵称、微信、手机号 -->
    <demo-block transparent>
      <wd-cell-group border custom-class="rounded-2! overflow-hidden">
        <wd-cell
          title="昵称"
          :value="profile.nickname"
          is-link
          @click="handleItemTap('昵称')"
        />
        <wd-cell
          title="微信"
          :value="profile.wechat"
          is-link
          @click="handleItemTap('微信')"
        />
        <wd-cell
          title="手机号"
          :value="profile.phone"
          is-link
          @click="handleItemTap('手机号')"
        />
      </wd-cell-group>
    </demo-block>

    <!-- 退出登录独立分组，文字居中 -->
    <demo-block transparent>
      <view
        class="mx-3 rounded-2 py-3 text-center text-4 wot-bg-filled-oppo wot-text-text-main"
        @click="handleLogout"
      >
        退出登录
      </view>
    </demo-block>
  </view>
</template>
