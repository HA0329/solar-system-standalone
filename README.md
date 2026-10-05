# 太阳系 · 实时三维模拟（Solar System — Real-time 3D Simulation）

一个基于 Three.js 构建的**单文件自包含**太阳系三维实时模拟网页。使用 NASA / Solar System Scope 真实表面贴图，行星按真实半径比例缩放，公转与自转周期均为真实值。

> 整个项目只有一个 HTML 文件，无任何外部依赖（three.js 库、贴图均已内嵌），下载后双击即可离线运行。

## 功能特性

- **真实数据驱动**：8 大行星按真实半径相对比例缩放；公转周期、自转周期、轴倾角均为真实值（金星逆向自转、天王星侧躺公转）
- **真实表面贴图**：14 张 2k 高清贴图（NASA / Solar System Scope），覆盖太阳、八大行星、月球、土星环、银河背景
- **地球细节**：夜景城市灯光、动态云层、带陨石坑的月球（真实轨道周期）
- **土星环 / 天王星暗环**：真实环带贴图，随自转轴倾角正确倾斜
- **小行星带**：1800 颗随机形状岩石，按开普勒速度分布运行
- **太阳效果**：泛光（Bloom）光晕 + 程序化星空 + 银河背景
- **完整交互**：
  - 点击行星聚焦并跟随，弹出真实数据卡片（半径 / 距日 / 周期 / 温度 / 卫星数等）
  - 模拟速度可调（暂停 ~ 365 天/秒）
  - 轨道线随距离淡出，贴近行星时不遮挡
  - 行星标签随距离淡出

## 操作指南

| 操作 | 功能 |
| --- | --- |
| 左键拖拽 | 旋转视角 |
| 滚轮 / 触控板 | 缩放 |
| 点击行星 | 聚焦并跟随行星，弹出数据卡片 |
| 空格 | 暂停 / 继续模拟 |
| Esc | 返回太阳系总览 |
| 底部导航栏 | 一键跳转太阳 / 各行星 |
| URL 加 `#saturn` | 打开页面直接聚焦土星（支持中文名 / 英文名 / ID） |

## 快速开始

```bash
# 方式一：直接双击 solar-system-standalone.html，用浏览器打开
# 方式二：本地起一个静态服务
python3 -m http.server 8000
# 浏览器访问 http://localhost:8000
```

需要支持 WebGL 的现代浏览器（Chrome / Edge / Firefox / Safari）。

## 数据说明

- **行星大小**：按真实半径比例缩放（地球 = 1.2 视觉单位）
- **轨道间距**：为便于观察采用压缩比例（`轨道半径 = 50 × AU^0.72`），未按真实距离等比
- **公转 / 自转周期、轴倾角**：真实值
- **轨道平面倾角**：采用真实黄道倾角（水星 7.0°、金星 3.4° 等）

## 技术栈

- [Three.js r128](https://threejs.org/)（含 OrbitControls、CSS2DRenderer、UnrealBloomPass）
- 原生 JavaScript + WebGL，无构建工具、无框架

## 目录结构

```
solar-system-standalone/
├── solar-system-standalone.html   # 唯一入口，单文件自包含（约 10MB）
├── README.md
└── LICENSE
```

## 素材与致谢

- 行星 / 太阳 / 土星环 / 银河贴图：**Solar System Scope**（[solarsystemscope.com/textures](https://www.solarsystemscope.com/textures/)），基于 NASA 影像数据，使用 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) 许可
- 3D 渲染引擎：Three.js（MIT License）
- 天文数据：NASA / JPL

## License

[MIT](LICENSE)
