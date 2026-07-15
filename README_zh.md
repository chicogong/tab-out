<div align="center">

# Tab Out (极简升级版)

**将您的“新标签页”转变为纯净、专注的标签管理控制台。**

![Tab Out Dashboard](assets/screenshot-v8.png)

<div>
  <a href="README.md">English</a>
  <span>&nbsp;|&nbsp;</span>
  <a href="README_zh.md">简体中文</a>
</div>
<br>

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Chrome Extension](https://img.shields.io/badge/Chrome-Manifest_V3-green.svg)](#)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-success.svg)](#)

</div>

## 项目简介

Tab Out 是一款轻量级的 Chrome 浏览器扩展。它通过接管默认的“新标签页”，将您当前打开的所有标签页按域名自动归类，聚合呈现为一个结构化的可视化仪表盘，帮助您快速理清工作思路，一键清理冗余网页。

本仓库是基于原版 Tab Out 深度重构的**极简升级版 (Minimalist Edition)**。我们秉持“少即是多”的设计哲学，大幅精简了冗余功能，并提升了底层代码的安全性和性能。

## 为什么选择此分支？

相较于原版仓库，本极简升级版（Minimalist Edition）进行了深入骨髓的架构与设计重构，为您带来极致的“控制台”体验：

- **🎨 硅谷级的高级美学 (Vercel / Linear Aesthetic)**：彻底废弃了原版繁杂、随意的样式。精心调校了每一个阴影、圆角与留白，采用无干扰的纯净底色与半透明卡片设计（Glassmorphism）。完美适配 macOS 原生质感，让每次打开新标签页都是一种视觉享受。
- **🧹 极致信息降噪**：大刀阔斧地砍掉了原版中容易引发信息焦虑的“稍后阅读 (Saved for Later)”侧边栏及收藏按钮。回归初心，构建绝对纯粹的单列网格布局，让你只专注于“此时此刻”正在处理的网页。
- **⚡️ 零延迟的响应速度**：重构了底层的 CSS 渲染树与动画引擎，移除了冗余的错开动画（Staggered delays）。整个界面加载快如闪电，操作极其清脆利落。
- **🛡️ 银行级的安全合规 (CSP & XSS)**：重构底层逻辑，彻底清除了所有的 `onclick`/`onerror` 内联事件，100% 满足 Chrome Manifest V3 最严苛的“内容安全策略”规范；为所有动态生成的标签页引入强制的 HTML 转义，根绝跨站脚本攻击。
- **🤖 智能仪表盘自动清理**：当您在任何窗口打开一个新的 Tab Out 标签页时，系统会在后台静默且自动地清理掉之前闲置的所有 Tab Out 面板。永远保证全网只有一个最新的仪表盘，彻底告别冗余。

## 核心功能

- **🗂️ 域名全自动聚合**：打开了 30 个标签页找不到想看的？Tab Out 会自动将杂乱无章的标签页按照所属域名（如 Github, Vercel, Figma）进行精美的网格化归类，一眼尽收眼底。
- **🌟 智能主页提取**：智能识别并提取常用 Web 应用（如 Gmail, X, YouTube, GitHub 等）的主页，并将其置顶在专属的 `Homepages` 卡片中，方便统一清理。
- **👯 查重专家 (Duplicate Detection)**：精准识别您不小心打开了多次的同一个网页！对于完全重复的标签，会醒目地打上极其精致的琥珀色 `(2x)` 甚至 `(3x)` 警告角标，并提供一键式 `Close 1 duplicate` 按钮，瞬间干掉多余分身，强迫症福音！
- **🚀 跨窗口瞬间穿梭**：点击仪表盘中的任意标签页标题，即可立刻跨越不同的浏览器窗口，瞬间聚焦定位到该网页，从此告别在几十个标签中迷失自我。
- **🔒 绝对的数据隐私**：100% 本地计算与渲染。无外部服务器，无数据库，无数据上报。您的所有浏览隐私数据绝不离开本地设备半步。
- **📦 零依赖轻量架构**：基于最纯粹的 Vanilla JavaScript 构建。无需 Node.js，无需 Webpack/Vite 编译，即下即用。

## 安装指南

### 手动加载安装

1. **克隆代码库：**
   ```bash
   git clone https://github.com/chicogong/tab-out.git
   ```

2. **在 Chrome 中加载：**
   - 在浏览器地址栏输入并访问 `chrome://extensions`。
   - 打开右上角的 **开发者模式 (Developer mode)** 开关。
   - 点击左上角的 **加载已解压的扩展程序 (Load unpacked)** 按钮。
   - 在弹出的文件选择器中，选中您刚刚克隆的仓库目录下的 `extension/` 文件夹。

3. **验证运行：**
   - 按下 `Cmd/Ctrl + T` 打开一个新标签页，即可看到 Tab Out 仪表盘。

## 技术栈说明

- **扩展框架**: Chrome Manifest V3
- **本地存储**: `chrome.storage.local`
- **UI 及动画**: 原生 HTML, CSS Grid 布局, 自定义 JS 粒子动画引擎
- **音频系统**: Web Audio API (动态实时合成音效，无静态音频资源)

## 开源协议

本项目基于 [MIT License](LICENSE) 协议开源。

<div align="center">
  <br>
  原作者 <a href="https://x.com/zarazhangrui">Zara</a> | 由 <b>Chico</b> 分支并重构升级为极简版
</div>
