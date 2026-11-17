<h1 align="center">
  BearPlan.UniApp
</h1>

<p align="center">BearPlan 移动端 App —— 基于 wot-starter（Wot UI）二次开发的 uni-app 多端应用</p>

## 简介

BearPlan.UniApp 是 BearPlan.NET 体系的移动端实现，面向小程序、App、H5 等多端场景。

本项目在 [wot-starter](https://github.com/wot-ui/wot-starter)（Wot UI 团队出品的 uni-app 起手模板）基础上搭建，使用 Vue 3 + Vite + TypeScript + Wot UI v2 技术栈。

## 技术栈

- ⚡️ [Vue 3](https://github.com/vuejs/core) + [Vite](https://github.com/vitejs/vite) + [pnpm](https://pnpm.io/) - 极速开发体验
- 🐂 [Wot UI V2](https://github.com/wot-ui/wot-ui) - 轻量、美观、AI 友好的 uni-app 组件库
- 🚦 [@wot-ui/router](https://github.com/wot-ui/my-uni) - 适用于 uni-app & Vue 3 的轻量级路由库
- 🌐 [Alova](https://alova.js.org/zh-CN/) - 极致高效的请求工具集
- 🎨 [UnoCSS](https://github.com/unocss/unocss) - 即时原子化 CSS 引擎
- 📊 [Uni Echarts](https://uni-echarts.xiaohe.ink/) - 适用于 uni-app 的 Apache ECharts 组件
- 🆒 [Uni Ku](https://uni-ku.js.org/) - uni-app 插件库
- 🔄 [Uni Mini CI](https://github.com/Moonofweisheng/uni-mini-ci) - 小程序端持续集成插件
- 🦾 [TypeScript](https://www.typescriptlang.org/) & [ESLint](https://eslint.org/) - 代码质量保障

## 快速上手

环境要求：Node.js >= 20.19.0，pnpm。

```bash
# 安装依赖
pnpm install

# H5 开发
pnpm dev:h5

# 微信小程序开发
pnpm dev:mp-weixin

# App 开发
pnpm dev:app
```

更多端命令见 `package.json` 中的 `dev:*` / `build:*` 脚本。

## 项目结构

```
.
├── src/            # 应用源码（页面、组件、布局、store 等）
├── docs/           # 文档站点（VitePress）
├── manifest.config.ts   # uni-app manifest 配置
├── pages.config.ts      # 页面路由配置
├── uno.config.ts        # UnoCSS 配置
└── vite.config.ts       # Vite 构建配置
```

## 鸣谢

本项目派生自以下优秀开源项目，衷心感谢：

- [wot-starter](https://github.com/wot-ui/wot-starter) - Wot UI 出品的 uni-app 起手模板，本项目的上游基础。
- [Wot UI](https://github.com/wot-ui/wot-ui) - 优秀的 uni-app 组件库。
- [uni-helper](https://github.com/uni-helper) - 为 uni-app 开发体验优化做出的贡献。
- [uni-ku](https://uni-ku.js.org/) - uni-app 插件生态。

## 开源协议

本项目基于 [MIT](https://zh.wikipedia.org/wiki/MIT%E8%A8%B1%E5%8F%AF%E8%AD%89) 协议开源。
Copyright (c) 2023-PRESENT KeJun
Copyright (c) 2026-PRESENT 围城 (BearPlan)
