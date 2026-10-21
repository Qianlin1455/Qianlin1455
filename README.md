# 👋 你好，我是 Qianlin

> 软件工程专业学生，当前主要关注 **Go 后端、分布式系统与 Agent**。

我喜欢从底层开始理解并构建系统：从事件驱动网络库、RPC 框架，到基于 Raft 的分布式存储，再到现在持续推进的 Go 后端、微服务与轻量级 Agent Runtime。

---

## 🧑‍💻 关于我

- 🎓 合肥工业大学软件工程专业大二学生
- 🚀 当前主线：**Go Backend / Microservices / Distributed Systems**
- 🤖 持续探索：**AI Agent Runtime / Tool Calling / MCP / RAG**
- ⚙️ 已完成：**Muduo 风格网络库 / RPC 框架 / Raft / 分布式 KV**
- 🌱 正在补强：**MySQL / Redis / gRPC / Kafka / 可观测性**
- 🧩 正在尝试参与真实开源项目，熟悉 Issue / PR / Review 流程
- 🎯 目标方向：**后端 / 分布式系统 / AI Infra 实习**

---

## 🛠 技术栈

### 编程语言

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

### 后端开发

![Gin](https://img.shields.io/badge/Gin-008ECF?style=flat-square&logo=gin&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-4285F4?style=flat-square&logo=google&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)

### 系统与基础设施

![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

### 关注方向

![Distributed Systems](https://img.shields.io/badge/Distributed_Systems-222222?style=flat-square)
![Network Programming](https://img.shields.io/badge/Network_Programming-222222?style=flat-square)
![Microservices](https://img.shields.io/badge/Microservices-222222?style=flat-square)
![Agent runtime](https://img.shields.io/badge/AI_Infra-222222?style=flat-square)

---

## 🚧 我正在做什么

### 1. Go 后端与微服务

目前正在系统推进 Go 后端技术栈，并计划通过一个完整微服务项目把各个知识点串起来。

```text
Gin
 ↓
MySQL / Redis
 ↓
gRPC
 ↓
Microservices
 ↓
Kafka
 ↓
Observability
 ↓
Distributed Systems
```

当前阶段重点：

- 使用 Go 构建结构清晰的 REST / RPC 服务
- 在真实项目中接入 MySQL 与 Redis
- 理解服务拆分、服务边界和微服务通信
- 学习 Kafka 与异步消息机制
- 增加日志、监控、链路追踪和性能分析
- 强化 Context、错误处理、测试和优雅关闭等工程能力

---

### 2. Go 轻量级 Agent Runtime

我正在使用 Go 构建一个轻量级 Agent Runtime，而不是简单套用现成 Agent 框架。

目前已经实现：

- LLM API 调用
- 多轮对话
- SSE 流式输出
- Function Calling
- Tool 注册与执行
- 多工具调用
- Context 取消与超时控制
- ReAct 风格 Agent Loop

计划继续加入：

```text
Model Gateway
    ↓
Tool Runtime
    ↓
Agent Loop
    ↓
Workflow / Graph
    ↓
Memory
    ↓
RAG / MCP
    ↓
Observability
```

我更关注 Agent 背后的 Runtime 问题，例如：

- 流式转发
- 工具超时隔离
- 重试 / 限流 / 熔断
- 并发编排
- 上下文管理
- Runtime 可观测性

---

## 🏗 代表项目

### ⚡ Raft 共识算法

仓库：[[Distributed_KV_Storage_System/raft at main · Qianlin1455/Distributed_KV_Storage_System](https://github.com/Qianlin1455/Distributed_KV_Storage_System/tree/main/raft)]

使用 C++ 独立实现 Raft 共识算法。

已实现：

- Leader Election
- 随机选举超时
- RequestVote RPC
- AppendEntries RPC
- 日志复制
- 多数派提交
- `nextIndex` / `matchIndex`
- Fast Backup
- 状态持久化
- State Machine Apply
- Snapshot 接口

核心状态：

```text
term
votedFor
log[]
commitIndex
lastApplied
nextIndex[]
matchIndex[]
```

通过这个项目重点理解了：

- 多数派交集为什么保证安全性
- Leader / Follower / Candidate 状态转换
- 日志冲突与覆盖规则
- commitIndex 与 lastApplied 的区别
- term 变化对节点状态的影响

---

### 🗄 分布式 KV 存储系统

仓库：[Qianlin1455/Distributed_KV_Storage_System](https://github.com/Qianlin1455/Distributed_KV_Storage_System)

在 Raft 基础上构建的分布式 Key-Value 存储系统。

核心请求链路：

```text
Client
  ↓
KV Server
  ↓
Raft::Start()
  ↓
日志复制
  ↓
多数派提交
  ↓
ApplyMsg
  ↓
State Machine
  ↓
Response
```

已实现：

- Put / Get / Delete
- 基于 Raft 的数据复制
- Client Request 幂等去重
- Pending Request 通知机制
- 线性一致性 Read Barrier
- SkipList 存储
- 数据持久化
- 超时与 Leader 校验

---

### 🌐 MPRPC

仓库：[Qianlin1455/MPRPC](https://github.com/Qianlin1455/MPRPC)

基于 TCP + Protobuf 实现的轻量级 C++ RPC 框架。

协议结构：

```text
4B frame length
+ 4B header length
+ RpcHeader
+ serialized arguments
```

已实现：

- 客户端 RPC Channel
- 服务端 RPC Provider
- Protobuf 反射机制
- Service / Method 注册
- 请求序列化
- 响应反序列化

该 RPC 框架后续也作为 Raft 中 RequestVote / AppendEntries 等 RPC 的通信基础。

---

### ⚙️ Muduo 风格网络库

使用 C++ 实现的事件驱动网络库。

核心组件：

```text
EventLoop
EpollPoller
Channel
Acceptor
TcpServer
TcpConnection
Buffer
ThreadPool
Logger
```

核心机制：

- Reactor 模式
- epoll
- 非阻塞 I/O
- eventfd 唤醒
- Main/Sub EventLoop
- Connection Callback
- Message Callback
- Write Complete Callback
- Graceful Shutdown

也对 EchoServer 做过压测，用于分析日志、I/O 路径等因素对吞吐量的影响。

---

### 🤖 Agent-Go

仓库：[Qianlin1455/Agent-Go-Loading-](https://github.com/Qianlin1455/Agent-Go-Loading-)

一个用于学习 Agent Runtime 架构的 Go 项目。

当前包括：

- DeepSeek Chat Completions
- SSE Streaming
- Tool Calls
- Weather Tool
- Calculator Tool
- 多 Step Agent 执行
- Tool Call Delta 组装
- 错误处理
- `maxSteps` 防死循环

---

## 🧠 我的技术兴趣

目前我的技术路线可以概括为：

```text
高性能后端
    ↓
分布式系统
    ↓
微服务
    ↓
AI Infrastructure
    ↓
Agent Runtime
```

正在持续学习：

- Go 并发
- Context 传播
- 网络编程
- RPC
- Raft
- MySQL 底层
- Redis
- Kafka
- 微服务架构
- 可观测性
- LLM Runtime
- Tool Calling
- RAG
- MCP

---

## 🌱 开源

目前正在逐步参与开源项目，并重点学习真实工程协作中的：

- Issue 分析
- Bug 复现
- Bug 修复
- 单元测试
- Code Review
- Pull Request
- CI
- Repository Convention

比较关注的开源方向：

- Go
- RPC
- 分布式系统
- 网络编程
- AI Infrastructure

---

## 📊 GitHub 数据

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Qianlin1455&show_icons=true&theme=github_dark&hide_border=true" />
</p>


<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Qianlin1455&layout=compact&theme=github_dark&hide_border=true" />
</p>


---

## 🧭 当前技术路线

```text
C++ Network Programming
        ↓
RPC Framework
        ↓
Raft
        ↓
Distributed KV
        ↓
Go Backend
        ↓
Microservices
        ↓
AI Agent Runtime
        ↓
AI Infrastructure
```

我希望把这些技术串成一条完整主线，而不是把它们当成彼此独立的知识点。

---

## 📫 联系方式

- GitHub：[@Qianlin1455](https://github.com/Qianlin1455)

---

<p align="center">
  <b>Build systems. Understand abstractions. Keep shipping.</b>
</p>




