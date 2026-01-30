# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

**Cyber Spirit 机器人底座** 是一个硬件开源项目，包含多模态 AI 情感陪伴机器人底座的完整设计文件。这不是传统的软件代码库，而是硬件设计资源集合。

## 项目文件

| 文件 | 用途 | 工具 |
|:---|:---|:---|
| `机器人底座外壳.stp` | 3D 外壳模型 (STEP 格式) | Creo/SolidWorks/Fusion 360 |
| `pcb工程文件.epro` | PCB 工程文件 | [立创 EDA](https://lceda.cn/) |
| `电池电路原理图.pdf` | 电池管理电路设计 | PDF 阅读器 |
| `舵机驱动电路原理图.pdf` | 舵机驱动电路设计 | PDF 阅读器 |

## 硬件架构

```
ESP32-S3 主控板 (外部)
        │ 8P排线
舵机驱动板 (PCA9685 PWM驱动)
        │ 8P排线
电池管理板 (LGS4056HDA充电 + SY7088DGC升压)
        │
锂电池 (PH2.0接口)
```

**机械执行**: 1 DOF，使用 Tower Pro MG90S 舵机 × 2

## 核心元器件

**电池板**: LGS4056HDA (充电管理) + SY7088DGC (DC-DC升压) + USB Type-C

**舵机驱动板**: PCA9685 (16通道PWM) + ESP32-S3连接器 + TF卡槽(可选)

## 开发工作流

### 3D 打印
```bash
# 1. 使用 CAD 软件打开 STEP 文件
# 2. 导出为 STL 格式
# 3. 打印参数: 层高 0.2mm, 填充率 20-30%
```

### PCB 制作
```bash
# 1. 使用立创 EDA 打开 .epro 文件
# 2. 直接下单打样或导出 Gerber 文件
```

## 相关资源

- 官方网站: https://cyberspirit.io
- 使用文档: https://docs.cyberspirit.io
- 演示视频: https://www.bilibili.com/video/BV16Lz9BJEWe

## 许可证

- 软件代码: MIT License
- 硬件设计: CERN Open Hardware Licence v2
