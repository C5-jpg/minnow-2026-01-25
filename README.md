<div align="center">

# 🌐 Minnow — Stanford CS144 计算机网络实验

**从零实现 TCP/IP 协议栈 · C++17 · 渐进式实验**

[![C++17](https://img.shields.io/badge/C%2B%2B-17-00599C.svg)](https://isocpp.org/)
[![CMake](https://img.shields.io/badge/CMake-3.24+-064F8C.svg)](https://cmake.org/)
[![Stanford](https://img.shields.io/badge/Stanford-CS144-8C151E.svg)](https://cs144.github.io/)

**ByteStream → Reassembler → TCP Sender/Receiver → Network Interface → IP Router**

</div>

---

## 📋 项目概述

本仓库是 **Stanford CS144 Introduction to Computer Networking** 课程实验框架 (代号 "Minnow")。学生从零开始实现一个完整的 **TCP/IP 协议栈**，从可靠的字节流到 IP 路由器，逐步构建网络协议的每一层。

> ⚠️ 请遵守课程要求：**不要公开分享实验解决方案**，以保持实验的教学价值。

Website: https://cs144.stanford.edu

### 🔑 渐进式实验设计

```
Lab 0          Lab 1           Lab 2          Lab 3          Lab 4
┌──────────┐  ┌────────────┐  ┌────────────┐  ┌───────────┐  ┌──────────┐
│ ByteStream│→ │ Reassembler │→ │TCP Sender  │→ │ Network   │→ │    IP    │
│ 可靠字节流 │  │ 流重组器    │  │+ Receiver  │  │ Interface │  │  Router  │
│           │  │ (乱序处理)  │  │ (完整TCP)  │  │ (ARP+IP)  │  │ (路由表) │
└──────────┘  └────────────┘  └────────────┘  └───────────┘  └──────────┘
```

---

## 📁 项目结构

```
minnow/
├── src/                  # 学生实现文件
│   ├── byte_stream.*     # Lab 0: 可靠字节流
│   ├── reassembler.*     # Lab 1: 流重组器
│   ├── tcp_sender.*      # Lab 2: TCP 发送端
│   ├── tcp_receiver.*    # Lab 2: TCP 接收端
│   ├── network_interface.* # Lab 3: 网络接口 (ARP)
│   └── router.*          # Lab 4: IP 路由器
├── tests/                # 40+ 测试文件
├── util/                 # 工具库 (Socket, TUN, Ethernet, IPv4, ARP)
├── apps/                 # 应用程序 (webget 等)
└── writeups/             # 实验报告模板
```

---

## 🚀 快速开始

```bash
# 配置
cmake -S . -B build

# 编译
cmake --build build

# 运行测试
cmake --build build --target test          # 全部测试
cmake --build build --target check0        # Lab 0 测试

# 性能基准
cmake --build build --target speed

# 代码格式化
cmake --build build --target format

# 静态分析
cmake --build build --target tidy
```

---

## 🛠️ 技术栈

| 类别 | 技术 |
|:---:|:---:|
| 语言 | C++17 |
| 构建 | CMake 3.24+ |
| 协议 | TCP/IP · ARP · Ethernet · IPv4 |
| 平台 | Linux (TUN, POSIX Socket) |
| 测试 | 自定义框架 (GoogleTest 风格) |

---

<div align="center">

**⭐ 如果这个项目对您有帮助，请给个 Star！**

</div>
