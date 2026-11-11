# @atooyu/uxto-ui

跨平台 UI 组件库，支持 **Android**、**iOS**、**鸿蒙** 三端打包。

[在线手册](https://jinguchu.github.io/uxto-ui/) | [源码手册](https://jinguchu.github.io/uxto-ui/guide/quickstart) | [快速开始](#快速开始) | [组件列表](#组件列表)

## 当前版本

`@atooyu/uxto-ui@1.2.1`（2026-11-10），详见 [更新日志](https://jinguchu.github.io/uxto-ui/guide/changelog.html)。修复独立 Checkbox、提供真实上传能力，并补齐全部 50 个组件类型声明。

## 安装

```bash
npm install @atooyu/uxto-ui
# 或
pnpm add @atooyu/uxto-ui
```

## 技术栈

- **框架**: uni-app + Vue 3 + TypeScript
- **构建**: Vite
- **样式**: SCSS

## 快速开始

### 安装依赖

```bash
npm install
```

### 开发模式

```bash
# H5
npm run dev:h5

# App (Android/iOS)
npm run dev

# 微信小程序
npm run dev:mp-weixin
```

### 构建打包

```bash
# App
npm run build:app

# 鸿蒙
npm run build:harmony

# H5
npm run build:h5

# 微信小程序
npm run build:mp-weixin
```

## 组件列表

### 基础组件
| 组件 | 说明 |
|------|------|
| u-button | 按钮 |
| u-cell | 单元格 |
| u-cell-group | 单元格组 |
| u-icon | 图标 |
| u-image | 图片 |
| u-divider | 分割线 |
| u-loading | 加载 |
| u-badge | 徽标 |
| u-tag | 标签 |
| u-avatar | 头像 |
| u-empty | 空状态 |
| u-skeleton | 骨架屏 |

### 表单组件
| 组件 | 说明 |
|------|------|
| u-input | 输入框 |
| u-textarea | 文本域 |
| u-switch | 开关 |
| u-slider | 滑块 |
| u-rate | 评分 |
| u-checkbox | 复选框 |
| u-radio | 单选框 |
| u-picker | 选择器 |
| u-datetime-picker | 时间选择器 |
| u-number-box | 数字输入框 |
| u-code-input | 验证码输入 |
| u-search | 搜索框 |
| u-upload | 上传 |

### 反馈组件
| 组件 | 说明 |
|------|------|
| u-modal | 弹窗 |
| u-popup | 弹出层 |
| u-toast | 轻提示 |
| u-loading-page | 加载页 |
| u-keyboard | 键盘 |
| u-tooltip | 文字提示 |
| u-notice-bar | 通知栏 |

### 导航组件
| 组件 | 说明 |
|------|------|
| u-tabbar | 底部导航 |
| u-swiper | 轮播图 |
| u-grid | 宫格 |
| u-list | 列表 |

### 展示组件
| 组件 | 说明 |
|------|------|
| u-line-progress | 进度条 |
| u-count-down | 倒计时 |
| u-parse | 富文本解析 |

### 其他组件
| 组件 | 说明 |
|------|------|
| u-layout | 布局 |
| u-link | 链接 |
| u-read-more | 展开阅读更多 |
| u-transition | 过渡动画 |

## 使用方式

按[快速配置](https://jinguchu.github.io/uxto-ui/guide/quickstart#快速配置)设置 easycom 路径与 SCSS 变量后，组件可自动导入：

```json
{ "easycom": { "autoscan": true, "custom": { "^u-(.*)": "@atooyu/uxto-ui/src/components/u-$1/u-$1.vue" } } }
```

```vue
<template>
  <u-button type="primary">按钮</u-button>
  <u-input v-model="value" placeholder="请输入" />
  <u-tabbar v-model="active" />
</template>
```

## 目录结构

```
uxto-ui/
├── src/
│   ├── components/       # 组件目录
│   │   ├── u-button/
│   │   ├── u-input/
│   │   └── ...
│   ├── pages/            # 页面目录
│   ├── styles/           # 样式文件
│   ├── App.vue
│   ├── main.ts
│   ├── manifest.json     # 应用配置
│   └── pages.json        # 页面配置
├── docs/                 # 文档目录
├── ecosystem/            # 生态工具
│   ├── cli/             # 命令行工具
│   ├── build/           # 构建配置
│   └── style/           # 样式系统
├── package.json
├── vite.config.ts
└── tsconfig.json
```

## Ecosystem 生态

### @uxto-ui/cli

命令行脚手架工具

```bash
# 安装
npm install -g @uxto-ui/cli

# 创建项目
uxto create my-app

# 添加组件
uxto add button
```

### @uxto-ui/style

样式系统和设计令牌

```scss
@use '@uxto-ui/style' as *;

.container {
  color: $uxto-primary;
  padding: $uxto-spacing-4;
}
```

### @uxto-ui/build

构建配置工具

```typescript
import { createUniBuildConfig } from '@uxto-ui/build'
```

## 发布到 NPM

### 构建组件库

```bash
npm run build:all
# build:types 会检查全部 50 个组件声明文件
```

### 发布

```bash
# 登录 npm
npm login

# 发布
npm publish
```

### 发布作用域包

```bash
npm publish --access public
```

## 打包说明

### Android 打包
1. 运行 `npm run build:app`
2. 使用 HBuilderX 云打包或离线打包

### iOS 打包
1. 运行 `npm run build:app`
2. 使用 HBuilderX 云打包或离线打包

### 鸿蒙打包
1. 运行 `npm run build:harmony`
2. 使用 DevEco Studio 打开项目打包

## 跨平台兼容性

所有组件都已适配以下平台：

- ✅ Android
- ✅ iOS
- ✅ 鸿蒙 (HarmonyOS)
- ✅ H5
- ✅ 微信小程序

### 兼容性处理

1. **安全区域**: 使用 `env(safe-area-inset-*)` 并添加鸿蒙兼容变量
2. **触摸事件**: 统一使用 `@click` 和 `@touchstart` 等事件
3. **API调用**: 使用 `uni.*` API 而非平台特定 API
4. **CSS属性**: 移除 `cursor` 等 Web-only 属性

## License

MIT