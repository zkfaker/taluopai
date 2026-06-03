# ✦ 宇宙塔罗牌 · 命运之约

> 基于手势控制的 3D 塔罗牌抽取互动网页，握拳选牌，张开亮牌。

![Tech Stack](https://img.shields.io/badge/Three.js-r160-049ef4?logo=threedotjs)
![Tech Stack](https://img.shields.io/badge/GSAP-3.12-88ce02?logo=greensock)
![Tech Stack](https://img.shields.io/badge/MediaPipe-Hands-ff6a00)

---

## ✨ 玩法

1. **五指张开** 面对屏幕，手掌左右摆动控制卡牌圆柱旋转
2. **握拳** 抓取正对屏幕的卡牌，飞至中央等待
3. **张开手掌** 展示卡牌内容——旋转 3 圈 → 金色粒子迸发 → 跳出展示

> 没有摄像头？点击屏幕同样可以选牌亮牌。

## 🛠 技术栈

| 技术 | 用途 |
|------|------|
| **Three.js** (r160) | 3D 渲染：卡牌圆柱、星空粒子、Bloom 后期发光 |
| **GSAP** (3.12) | 卡牌飞入、旋转、抖动、粒子散射动画 |
| **MediaPipe Hands** | 21 点手部关键点识别、握拳/张开手势检测 |
| **EffectComposer** | UnrealBloomPass 后期特效 |

## 📁 文件结构

```
taluopai/
├── index.html    ← 单文件应用（HTML + CSS + JS 全部内联）
├── README.md     ← 项目说明
└── CLAUDE.md     ← 开发文档
```

## 🚀 本地运行

```bash
npx serve .
# 或
python -m http.server 8080
```

然后浏览器打开 `http://localhost:8080`。

> 需要本地服务器是因为 Three.js 使用 ES Module importmap，不能直接双击打开。

## 🌐 在线体验

访问 [https://zkfaker.github.io/taluopai](https://zkfaker.github.io/taluopai)

## 🎴 卡牌一览

- **银河之眼** ·  **星云之门** ·  **暗影领主** ·  **星辰之女**
- **虚空使者** ·  **凤凰涅槃** ·  **冰霜巨龙** ·  **命运之轮**

每张卡牌的正面纹理由 Canvas 动态生成，可在 `window.PHOTO_BASE64` 替换为真实图片。

## 📱 兼容性

- 桌面端 Chrome / Edge / Firefox（推荐）
- 移动端 Safari / Chrome（手势识别取决于设备摄像头支持）
- 无摄像头环境自动降级为点击交互
