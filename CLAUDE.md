# 宇宙级3D卡牌抽取互动网页

## 角色设定
资深前端开发工程师 + WebGL互动视觉专家

## 项目概述
单文件（HTML+CSS+JS）宇宙主题3D卡牌抽取互动网页，开箱即用，所有外部依赖通过CDN引入。

## 技术栈
- **3D渲染**: Three.js (r160+) + EffectComposer + UnrealBloomPass
- **动画引擎**: GSAP 3.12
- **手势交互**: Google MediaPipe Hands + Camera Utils
- **UI设计**: 深色主题 + 磨砂玻璃质感 (backdrop-filter)

## 核心功能
1. 全局错误捕获（JS错误 + Promise rejection），底部fixed红色浮层显示
2. 全屏加载遮罩（渐变进度条），完成后入场动画层（含"跳过"按钮）
3. 动态3D星空粒子背景 + Bloom后期发光特效
4. 顶部悬浮Header（glassmorphism），含集卡进度条
5. 摄像头手势控制（MediaPipe），pinch捏合触发抽卡
6. 3D卡牌翻转动画 + Toast反馈
7. 响应式移动端适配
8. 摄像头不可用时降级为点击/触摸抽卡

## 文件结构
- `index.html` — 单文件应用（所有HTML/CSS/JS内联）
- `CLAUDE.md` — 项目文档

## 开发指南
- 所有外部依赖通过CDN引入（Three.js importmap + GSAP/MediaPipe script tags）
- 卡牌图片使用 Canvas 生成（预留 PHOTO_BASE64 对象便于后续替换为真实图片）
- 修改后直接刷新浏览器即可预览（需本地服务器 due to ES module CORS）
- 默认 8 张宇宙主题卡牌

## 启动方式
```bash
# 使用任意本地服务器启动（因 ES module 需要）
npx serve .
# 或
python -m http.server 8080
# 然后浏览器打开 http://localhost:8080
```
