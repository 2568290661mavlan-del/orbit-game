# 回旋 ORBIT

一款由 **1 人 + 豆包 AI 协作完成**的离线弹幕生存 roguelite：恒速飞行、鼠标瞄准，用飞行轨迹画出闭环，引爆圈内的敌人。

## 直接试玩

仓库根目录的 [`index.html`](index.html) 就是完整游戏，下载后双击即可运行，**完全离线、无需安装依赖**。

启用 GitHub Pages（Settings → Pages → Deploy from a branch → `main` / `root`）后，也可以直接通过 `https://<用户名>.github.io/<仓库名>/` 在线试玩。

## 操作

- **空格 / Enter**：开始
- **WASD / 方向键**：转向（机体恒速前进，没有刹车）
- **鼠标**：瞄准，武器自动开火
- **R**：切换破甲 / 守护；也可按住 Shift 或鼠标右键临时破甲
- **Esc / P**：暂停；**O**：设置；**T**：重看教学
- 主菜单 **C**：从检查点继续；**V**：回滚到上一个检查点

## 核心玩法

- **守护姿态**：闭环聚拢敌人、清除敌弹，并将子弹转化为能量球。
- **破甲姿态**：高伤拆甲、击退装甲目标，拆甲击杀掉落能量核心。
- 开枪消耗能量，套圈补充能量；伤害主要由「这一圈套住了几只」决定，大圈不会被面积上限吞掉。
- 三步交互教学、三章生存流程、小 Boss 与终局旗舰、20 项升级及组合、三档难度、检查点回滚、按键重映射、中英文界面。

## 从源码复现

需要 Node.js 22+ 与 PowerShell 7：

```powershell
pwsh -File tools/build.ps1
```

该命令会安装构建依赖、运行 **134 条自动化测试**，然后生成 `build/index.html`。

其他验收工具：

```powershell
node tools/probe.mjs 900 20261125   # 自动驾驶平衡探针
node tools/soak.mjs 30              # 30 分钟连续对局稳定性测试
```

## 文档与素材

- [怎么玩](docs/README.md)
- [设计文档 GDD](docs/GDD.md)
- [更新日志](docs/CHANGELOG.md)
- [验收记录 QA](docs/QA.md)
- [素材授权](assets/LICENSE.md)

机体、敌机与贴图来自 Kenney Space Shooter Redux（CC0），音效来自 Kenney Interface / Sci-Fi（CC0），授权原文随仓库保留。

## 协作方式

玩法方向、真人试玩反馈、问题定位与验收由人负责；代码实现、自动化测试、性能优化、构建和文档由豆包 AI 协作完成。
