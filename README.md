# 跳一跳 · 网页版

参照微信「跳一跳」小游戏制作的网页版跳格子游戏。**单 HTML 文件、零依赖、离线可玩**。

## 在线试玩

https://lywdejava.github.io/wechat-jump-game/

## 玩法

- **按住**鼠标左键 / 触摸屏幕 / 空格键蓄力，**松开**起跳
- 跳上下一个方块 **+1 分**
- 落在方块**中心区域**触发「完美」，连击奖励 **+2 / +4 / +8 …**（封顶 32）
- 跳过头或没踩中方块 → 掉落，游戏结束
- 最高分自动保存到浏览器 localStorage

## 特性

- 🎨 浅蓝色系极简配色，Canvas 2D 手绘等轴测伪 3D（无 WebGL）
- 🧊 方块随机造型：方体 / 圆柱，随机浅蓝白配色点缀
- 📈 难度渐进：间距随分数变大、方块略微缩小
- ✨ 细节动效：蓄力下蹲、跳跃挤压拉伸、落地圆环扩散、连击粒子、掉落旋转
- 📷 相机平滑跟随当前方块
- 🔊 WebAudio 程序合成音效（右上角一键静音）
- 📱 桌面 / 移动端自适应，devicePixelRatio 高清渲染
- 💾 最高分本地持久化

## 本地运行

直接用浏览器打开 `index.html` 即可，无需服务器与构建步骤。

或起一个静态服务器：

```bash
python -m http.server 8080
# 访问 http://localhost:8080
```

## 技术栈

原生 HTML + CSS + JavaScript（Canvas 2D + requestAnimationFrame + WebAudio），
状态机驱动：`TITLE → READY → CHARGE → JUMP → FALL → OVER`。

## 可调参数

难度相关参数集中在脚本顶部：

| 参数 | 说明 |
|------|------|
| `CHARGE_TIME` | 蓄满所需时长 |
| `MIN_DIST` / `MAX_DIST` | 最小 / 最大跳跃距离 |
| `diffLevel()` | 间距随分数的难度公式 |

## 许可

MIT
