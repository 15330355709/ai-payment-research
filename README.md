# AI 支付研究 - 知识库目录

> 本目录索引 AI 支付领域的研究资料，各主题拆分为独立文件，便于查阅和维护。

---

## 文件结构

```
AI支付研究/
├── AP2协议研究笔记.md          ← 你在这里（目录索引）
├── AI支付科普与协议全景.md      ← 入门必读：全景科普
├── 01-AP2协议详解.md           ← Google AP2 协议深度分析
├── 02-x402协议详解.md          ← x402 + A2A x402 协议深度分析
├── 03-Stripe产品分析.md        ← Stripe ACP + 超越支付产品线
├── 04-Circle产品分析.md        ← Circle USDC + 可编程钱包
├── 05-竞争格局与战略分析.md     ← 四大玩家卡位与竞合关系
└── 新闻列表.md                 ← 新闻动态追踪
```

---

## 阅读顺序建议

### 如果你是第一次接触 AI 支付

1. **[AI支付科普与协议全景.md](AI支付科普与协议全景.md)** — 从零建立全景认知
   - 什么是 AI 支付？三种场景
   - MCP、A2A、ADK 基础协议
   - AP2、ACP、x402、TAP 支付协议对比
   - 术语速查表

### 如果你想深入了解某个协议

2. **[01-AP2协议详解.md](01-AP2协议详解.md)** — Google 的 AP2 协议
   - Mandate（授权凭证）核心机制
   - VDC 的技术本质与存储方式
   - 角色架构与数据流转
   - 60+ 生态参与方

3. **[02-x402协议详解.md](02-x402协议详解.md)** — Coinbase 的 x402 + Google 的 A2A 扩展
   - x402 底层协议原理
   - A2A x402 支付流程与状态机
   - 密钥安全：原版 vs A2A 扩展
   - Google 在原版上的 6 大增强

### 如果你想了解各公司的产品与战略

4. **[03-Stripe产品分析.md](03-Stripe产品分析.md)** — Stripe 全产品线分析
   - ACP 协议 + Agentic Commerce Suite
   - SharedPaymentToken (SPT) 机制
   - 加密货币、智能体商务、机器支付三条产品线
   - 产品协同与战略逻辑

5. **[04-Circle产品分析.md](04-Circle产品分析.md)** — Circle 产品分析
   - USDC 发行与商业模式
   - Developer-Controlled Wallets (MPC)
   - x402 集成实战 Demo
   - "卖水"战略逻辑

6. **[05-竞争格局与战略分析.md](05-竞争格局与战略分析.md)** — 四大玩家竞合
   - Google 的 5 个角色卡位
   - Coinbase 的 4 个角色卡位
   - 入场方式 / 产品 / 商业模式 / 竞合关系对比
   - 两大阵营：Google+Coinbase vs Stripe+OpenAI

---

## 核心概念速查

| 缩写 | 全称 | 开发者 | 文件 |
|------|------|--------|------|
| **AP2** | Agent Payments Protocol | Google | [01-AP2协议详解.md](01-AP2协议详解.md) |
| **ACP** | Agentic Commerce Protocol | Stripe + OpenAI | [03-Stripe产品分析.md](03-Stripe产品分析.md) |
| **x402** | HTTP 402 Payment Protocol | Coinbase | [02-x402协议详解.md](02-x402协议详解.md) |
| **MCP** | Model Context Protocol | Anthropic | [AI支付科普与协议全景.md](AI支付科普与协议全景.md) |
| **A2A** | Agent2Agent Protocol | Google | [AI支付科普与协议全景.md](AI支付科普与协议全景.md) |
| **SPT** | SharedPaymentToken | Stripe | [03-Stripe产品分析.md](03-Stripe产品分析.md) |
| **VDC/Mandate** | Verifiable Digital Credential | Google (AP2) | [01-AP2协议详解.md](01-AP2协议详解.md) |
| **USDC** | USD Coin | Circle | [04-Circle产品分析.md](04-Circle产品分析.md) |

---

*最后更新: 2026-02-28*
