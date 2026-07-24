# ♟ Gobang — 基于权值评分算法的五子棋

![C++](https://img.shields.io/badge/Language-C++-blue.svg)
![EasyX](https://img.shields.io/badge/Graphics-EasyX-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)
[![Play Online](https://img.shields.io/badge/🎮-Play%20Online-e94560.svg)](https://horikitax.github.io/C-gobang)

> 一个基于 **C++ + EasyX** 的经典五子棋对弈系统，支持**人机对战**。
> 电脑决策通过遍历棋盘空位、按预设棋型分值表计算得出。

---

## 🎮 在线试玩

[**👉 点我直接下棋**](https://horikitax.github.io/C-gobang)

无需安装，浏览器打开即玩！支持 **人机对战** 和 **双人模式** 切换。

---

## ✨ 核心特性

| 特性 | 说明 |
|:-----|:------|
| **权值评分决策** | 遍历棋盘空位，按预设棋型分值表计算攻防评分，选取最优落子 |
| **面向对象设计** | 封装 `box`（棋格）与 `seat`（位置评分）类，UI 与逻辑解耦 |
| **图形化交互** | 基于 EasyX 图形库，支持 19×19 棋盘、鼠标悬停高亮、落子动效 |
| **完整判定逻辑** | 四方向扫描，判定五连珠、平局及禁手 |

---

## 🧠 决策原理

### 权值评分 (`findbestseat`)

每一步棋经过以下评估流程：

```
TotalScore = Score_进攻 × 4 + Score_防守
```

1. **双向扫描**：对棋盘每个空位进行四个方向（水平、垂直、两条对角线）的特征提取
2. **棋型识别**：识别活三、冲四、连五等关键棋型
3. **评分表匹配**：根据棋型匹配预设分值，进攻权重加权
4. **随机选取**：从多个同分候选位置中随机选取，增加变化性

### 评分表

| 棋型 | 被挡次数 | 分值 |
|:----|:--------:|:----|
| 连五 | — | **92840** |
| 活四 | 0 | 5800 |
| 活三 | 0 | 360 |
| 冲四 | 1 | 360 |
| 活二 | 0 | 20 |

---

## 🛠️ 快速开始

### 环境要求

| 依赖 | 版本 |
|:----|:----|
| 操作系统 | Windows 10/11 |
| IDE | Visual Studio 2022+ |
| 图形库 | [EasyX](https://easyx.cn/) |

### 运行步骤

```bash
# 1. 克隆仓库
git clone https://github.com/Horikitax/C-gobang.git
cd C-gobang

# 2. 安装 EasyX（在 VS 中安装插件）
#    项目 → 管理 NuGet 程序包 → 搜索 EasyX

# 3. 用 Visual Studio 打开 gobang.cpp，编译运行
```

---

## 🌐 项目结构

```
C-gobang/
├── gobang.cpp          # 主程序（C++，EasyX 图形界面）
├── README.md           # 项目文档
├── index.html          # 🌟 网页版预览 (gh-pages)
└── .gitignore
```

---

## 📜 License

Copyright © 2024 [Horikitax](https://github.com/Horikitax). MIT License.
