# Gobang (Five-in-a-Row) — C++ & EasyX

![C++](https://img.shields.io/badge/Language-C++-blue.svg)
![EasyX](https://img.shields.io/badge/Graphics-EasyX-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)
[![Play Online](https://img.shields.io/badge/Play-Online%20Demo-e94560.svg)](https://yox1no.github.io/C-gobang)

A classic Gobang (Five-in-a-Row) game implemented in **C++** with the **EasyX** graphics library, featuring a weighted heuristic AI opponent.

---

## Online Demo

[**Play in Browser**](https://yox1no.github.io/C-gobang)

No installation required. Supports both **Player vs. AI** and **Two-Player** modes.

---

## Features

| Feature | Description |
| :--- | :--- |
| **Weighted Heuristic AI** | Evaluates every empty cell using pattern-based offensive and defensive scores to choose the optimal move |
| **Object-Oriented Design** | Separates board cells (`box`) and position scoring (`seat`) to decouple game logic from UI rendering |
| **Graphical Interface** | Built on EasyX with a 19×19 board, hover highlights, and move feedback |
| **Complete Rule Checking** | Four-direction scanning for five-in-a-row win detection, draw detection, and forbidden moves |

---

## AI Decision Logic

### Weighted Evaluation (`findbestseat`)

Each candidate move is scored as:

```text
TotalScore = OffensiveScore * 4 + DefensiveScore
```

1. **Four-Direction Scan**: Extracts pattern features along horizontal, vertical, and two diagonal axes for every empty cell.
2. **Pattern Recognition**: Identifies key formations such as Live Three, Rush Four, and Five-in-a-Row.
3. **Score Lookup**: Assigns weights from the pattern score table with higher priority on offensive threats.
4. **Tie-Breaking**: Randomly selects among equally top-scored candidates to add variety.

### Pattern Score Table

| Pattern | Blocked Ends | Score |
| :--- | :---: | :--- |
| Five-in-a-Row | — | **92840** |
| Open Four | 0 | 5800 |
| Open Three | 0 | 360 |
| Half-Open Four | 1 | 360 |
| Open Two | 0 | 20 |

---

## Getting Started

### Requirements

| Dependency | Version |
| :--- | :--- |
| OS | Windows 10 / 11 |
| IDE | Visual Studio 2022+ |
| Graphics Library | [EasyX](https://easyx.cn/) |

### Build & Run

```bash
# 1. Clone the repository
git clone https://github.com/Yox1no/C-gobang.git
cd C-gobang

# 2. Install EasyX in Visual Studio
#    Project -> Manage NuGet Packages -> Search "EasyX"

# 3. Open gobang.cpp in Visual Studio, build, and run
```

---

## Project Structure

```text
C-gobang/
├── gobang.cpp          # Main C++ source (EasyX GUI + heuristic AI)
└── README.md           # Project documentation
```

---

## License

Copyright © 2024 [Yox1no](https://github.com/Yox1no). Released under the MIT License.
