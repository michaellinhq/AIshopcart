# 购物跟随车 / 个人助理机器人

## 项目简介

本项目旨在打造一个基于视觉追踪的四轮驱动小车，并结合可升降平台，形成"购物跟随车"或"个人助理机器人"。该系统可自动跟随用户、避障、承载物品，并通过升降机构方便取放，适合超市购物、助老助残等场景。

## 核心功能
- **视觉追踪**：识别并跟随目标人物，自动避障。
- **升降机构**：平台可升降，便于物品存取。
- **物品承载**：具备一定载重能力。
- **自主导航**：复杂环境下路径规划与避障。

## 系统架构
- **树莓派 4B**：负责视觉识别、路径规划、与ESP32通信。
- **ESP32**：负责电机/升降机构的实时控制，接收树莓派指令。
- **升降平台**：采用跑步机电机+减速机构/丝杠驱动。
- **四轮底盘**：直流减速电机驱动，带编码器实现闭环控制。
- **多传感器融合**：摄像头、超声波/ToF传感器等。

## 项目分步指南
1. **升降机构原型**：搭建升降平台，测试电机驱动与限位保护。
2. **小车底盘搭建**：安装电机、轮子，测试基本移动。
3. **视觉追踪实现**：树莓派OpenCV目标检测与跟随。
4. **系统集成**：树莓派与ESP32串口通信，联动升降与移动。
5. **测试与优化**：多场景测试，完善避障、承载与用户交互。

## 物料清单（德国采购优化）

| 序号 | 部件名称           | 规格/型号（示例）                | 数量 | 主要功能           | 购买渠道（德国）         | 备注 |
|------|--------------------|-----------------------------------|------|--------------------|--------------------------|------|
| 1    | 树莓派 4B          | Raspberry Pi 4B                   | 1    | 主控/视觉          | -                        |      |
| 2    | ESP32开发板        | ESP32-WROOM-32                    | 1    | 电机/传感器控制    | Conrad, Reichelt, Amazon |      |
| 3    | 直流减速电机       | 12V 带编码器 60-200RPM            | 2-4  | 驱动轮子           | Conrad, eBay, Pololu     |      |
| 4    | 电机驱动模块       | TB6612FNG/BTS7960                 | 1-2  | 控制电机           | Conrad, Reichelt         |      |
| 5    | 跑步机电机         | 0.8kW                             | 1    | 升降平台           | eBay, Amazon             |      |
| 6    | 蜗轮蜗杆/丝杠      | 适配电机                          | 1    | 升降减速/驱动      | Conrad, eBay             |      |
| 7    | 轮子               | 65mm 橡胶轮                       | 2-4  | 移动               | Conrad, Amazon           |      |
| 8    | DC-DC降压模块      | LM2596/MP1584EN                   | 1-2  | 电源转换           | Conrad, Amazon           |      |
| 9    | 锂电池/电池模块    | 适配电机/控制板                   | 1    | 电源               | Conrad, Amazon           |      |
| 10   | 充电器             | 适配电池                          | 1    | 电池充电           | Conrad, Amazon           |      |
| 11   | 树莓派摄像头模块   | Pi Camera v2/HQ/优质USB摄像头     | 1    | 视觉采集           | Conrad, BerryBase        |      |
| 12   | 超声波传感器       | HC-SR04                           | 2-4  | 障碍物检测         | Conrad, Amazon           | 可选 |
| 13   | 连接线/跳线        | 杜邦线/硅胶线                     | 若干 | 连接各模块         | Conrad, Amazon           |      |
| 14   | 螺丝螺母套件       | M2/M3/M4                          | 若干 | 结构固定           | 五金店, Amazon           |      |
| 15   | SD卡               | ≥16GB, Class 10                   | 1    | 树莓派系统          | 各大电子市场             |      |
| 16   | 3D打印耗材         | PLA/ABS等                         | 若干 | 结构件打印         | Amazon, Conrad           |      |

## 所需技能
- Python编程（树莓派端）
- MicroPython/嵌入式开发（ESP32端）
- 电机与H桥驱动原理
- 编码器/限位开关应用
- 机械结构设计与3D打印
- OpenCV视觉算法
- 串口通信（UART）
- PID控制基础
- 系统集成与调试

## 推荐学习资源
- [MicroPython官方文档](https://docs.micropython.org/)
- [RandomNerdTutorials（ESP32/ESP8266）](https://randomnerdtutorials.com/)
- [树莓派官方文档](https://www.raspberrypi.com/documentation/)
- [OpenCV官方Python教程](https://docs.opencv.org/master/d6/d00/tutorial_py_root.html)
- [PyImageSearch博客](https://www.pyimagesearch.com/)
- [YouTube: Andreas Spiess](https://www.youtube.com/@AndreasSpiess)
- [Q-engineering: 树莓派DNN部署](https://qengineering.eu/installing-opencv-on-raspberry-pi.html)
- [Coursera/edX/Udemy: Robotics, Embedded Systems, Computer Vision]
- [Raspberry Pi/ESP32论坛, Stack Overflow]

## 部署与开发建议
1. **先实现ESP32电机控制**，确保底盘和升降机构可控。
2. **树莓派实现视觉识别与串口通信**，完成基本跟随。
3. **逐步集成与测试**，优化结构与算法。
4. **关注电源管理与安全保护**。

---

> 本项目适合机器人、嵌入式、计算机视觉等方向的学习与实践。欢迎在GitHub上Fork、改进和交流！ 