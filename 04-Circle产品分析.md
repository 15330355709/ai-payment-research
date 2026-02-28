# Circle 产品分析 — USDC 与可编程钱包

> 本文分析 Circle 在 AI 代理支付领域的产品布局，包括 USDC 稳定币、Developer-Controlled Wallets 和 x402 集成。

## Circle 的入场方式：USDC + 可编程钱包 + x402

- **来源**: [Circle Blog - Autonomous Payments](https://www.circle.com/blog/autonomous-payments-using-circle-wallets-usdc-and-x402)
- **核心产品**: Developer-Controlled Wallets + USDC + x402 集成
- **开发者文档**: [Circle Docs](https://developers.circle.com/)

## 1 一句话理解

> Google 做协议标准，Stripe 做商户工具，Coinbase 做清算基础设施。
> **Circle 的思路是"让 USDC 成为 AI 代理世界的默认货币"。**
>
> 不管你用什么协议、什么平台，只要代理之间要转钱，就用 USDC。

## 2 Circle 是谁？

Circle 是 **USDC（美元稳定币）的发行方**。USDC 是目前市值第二大的稳定币，1 USDC = 1 美元，由美元储备 1:1 支撑。Circle 的核心商业模式：

```
用户/企业 → 存入美元 → Circle 发行等量 USDC
                     → Circle 把美元存入国债/银行
                     → 靠储备金利息赚钱（年化数十亿美元）

流通的 USDC 越多 → Circle 赚的利息越多
```

**所以 Circle 的核心利益是：让 USDC 在尽可能多的场景中流通。AI 代理支付是一个巨大的增量场景。**

## 3 核心产品组合

Circle 为 AI 代理支付提供了三层产品：

```
┌──────────────────────────────────────────────┐
│  第三层：协议集成                               │
│  · x402 协议支持（HTTP 原生支付）               │
│  · AP2 协议合作（Google 生态）                  │
│  · MCP Server（开发者 IDE 集成）               │
├──────────────────────────────────────────────┤
│  第二层：钱包即服务（WaaS）                     │
│  · Developer-Controlled Wallets               │
│  · MPC 密钥管理（私钥不暴露）                   │
│  · 多链支持（EVM + Solana）                    │
│  · EOA 和智能合约账户                           │
├──────────────────────────────────────────────┤
│  第一层：货币层                                │
│  · USDC 发行和赎回                             │
│  · 跨链转账（CCTP 协议）                        │
│  · Testnet 水龙头（开发测试用）                  │
└──────────────────────────────────────────────┘
```

#### Developer-Controlled Wallets（核心产品）

Circle 的钱包方案与 Coinbase CDP 的定位不同：

| 维度 | Coinbase CDP Wallet | Circle Developer-Controlled Wallets |
|------|--------------------|------------------------------------|
| **托管模式** | TEE（可信执行环境） | MPC（多方计算） |
| **控制权** | 开发者通过 API 调用 | 开发者完全控制钱包操作 |
| **定位** | x402 生态的默认钱包 | 通用的"钱包即服务" |
| **特点** | 跟 Coinbase 交易所打通 | 跟 USDC 发行/赎回打通 |

MPC（多方计算）的原理用一句话解释：**把一把钥匙拆成多片，分别存在不同地方，签名时各片协作计算，但完整钥匙从不在任何一个地方出现过。**

## 4 Circle 的 AI 代理支付场景

Circle 已经实现了一个完整的 Demo（使用 LangChain + GPT-4o mini）：

```
AI 代理想查询某个钱包的风险评分（一个付费 API）

① 代理调用 Circle API 创建钱包
② 代理调用 Circle 水龙头 API 给钱包充值 USDC
③ 代理请求风险评分 API → 收到 402 (需支付 $0.01)
④ 代理调用 Circle 签名 API，签署支付授权
⑤ 代理重发请求 + 支付签名 → 服务端验证 → 链上结算
⑥ 代理收到风险评分数据

全程无人工干预，代理自己创建钱包、充值、付费、拿数据。
```

## 5 Circle 的战略逻辑

**入场方式：从"货币层"切入，"卖水"策略**

```
淘金热中谁最赚钱？不是挖金子的人，是卖水的。

AI 代理支付的"淘金热"中：
  · Google 在卖"矿区地图"（协议标准）
  · Stripe 在卖"挖矿工具"（商户接入套件）
  · Coinbase 在卖"淘金铲子"（清算基础设施）
  · Circle 在卖"水"（USDC，代理之间流通的货币本身）

不管谁的协议赢了、谁的工具好用，
只要代理之间用 USDC 交易，Circle 就赚钱。
```

Circle 的策略是**与所有协议兼容**，而不是自己做协议：

| 协议生态 | Circle 的角色 |
|---------|-------------|
| **x402 (Coinbase)** | USDC 是默认支付代币 + Circle Wallet 是替代钱包方案 |
| **AP2 (Google)** | AP2 的 x402 扩展使用 USDC 结算 |
| **ACP (Stripe/OpenAI)** | 未来可作为加密支付选项 |
| **通用场景** | 任何 AI 代理的钱包都可以持有和转移 USDC |

---

*本文件从 AP2协议研究笔记.md 拆分而来 | 最后更新: 2026-02-28*

