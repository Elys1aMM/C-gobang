# Gobang-AI: 基于权值评分算法的智能五子棋系统

![C++](https://img.shields.io/badge/Language-C++-blue.svg)
![Graphics](https://img.shields.io/badge/Library-EasyX-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

## 📝 项目简介
本项目是一个基于 **C++** 开发的经典五子棋对弈系统，集成了图形化界面与 AI 对战功能。项目核心实现了一套基于**启发式权值搜索**的决策引擎，能够实现初级的人机对战，适合作为 C++ 编程基础与博弈算法入门的实践案例。

## 🚀 核心特性
- **启发式 AI 引擎**：AI 通过遍历棋盘空位，结合预设的“五子棋型分值表”计算进攻与防守权值，自动选取最优落子点。
- **面向对象开发**：封装 `box`（棋格）与 `seat`（位置评分）类，解耦 UI 渲染与逻辑运算，代码结构清晰。
- **图形化交互方案**：基于 **EasyX** 图形库构建，支持标准 19x19 棋盘绘制、鼠标悬停实时高亮指示、下棋落子动效。
- **完善的逻辑判定**：内置四方向扫码算法，精确判定五连珠（胜）、平局及禁手逻辑。



## 💡 技术实现深度解析

### 1. AI 决策逻辑 (Heuristic Search)
AI 的每一步棋都经过以下评估流程：
- **评估函数**：$TotalScore = Score_{Attack} \times 4 + Score_{Defense}$。
- **双向扫描**：对棋盘每一个空位进行四个方向（水平、垂直、两条对角线）的特征提取，识别出“活三”、“冲四”等关键棋型。
- **评分表机制**：根据当前棋型匹配对应的分值（如连五 > 活四 > 活三），并对进攻权重进行加权处理，使 AI 表现更具进攻性。

### 2. 坐标与渲染系统
- 采用像素级坐标转换，将鼠标点击位置动态映射至 $19 \times 19$ 的二维数组。
- 利用双缓冲思想（EasyX 内置处理）实现棋盘的重绘，确保界面无闪烁。

## 🛠️ 开发环境
- **操作系统**: Windows 10/11
- **集成开发环境 (IDE)**: Visual Studio 2022
- **图形库依赖**: [EasyX Graphics Library](https://easyx.cn/) (请确保已安装 EasyX 插件)

## 📦 快速上手
1. **配置环境**：在 Visual Studio 中安装 EasyX 插件。
2. **克隆项目**：
   ```bash
   git clone [https://github.com/YourUsername/Gobang-AI.git](https://github.com/YourUsername/Gobang-AI.git)
