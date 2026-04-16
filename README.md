# 多空绞肉机 · Long-Short Meat Grinder v1.0

> **"当一方仓位极度拥挤时，清算瀑布就是印钞机。"**

基于多空比 + 持仓量 + 资金费率三重共振的清算瀑布捕捉策略，专为 OKX Agent Trade Kit 设计。

## 策略简介

| 维度 | 说明 |
|------|------|
| **核心逻辑** | 多空比 × 持仓量 × 资金费率三重共振检测 |
| **Alpha 来源** | 杠杆交易者的强制平仓（清算瀑布） |
| **适用账户** | 100 – 1,000 USDT 小资金账户 |
| **执行周期** | 4H |
| **主要标的** | BTC / ETH / SOL 永续合约 |
| **杠杆上限** | BTC 3x / ETH 2x / SOL 2x |

## 绞肉信号矩阵

| 多空比 | 持仓量 | 费率 | 信号 |
|--------|--------|------|------|
| L/S > 2.0（多头拥挤） | OI 新高 | > +0.05% | **做空（多头即将被绞）** |
| L/S < 0.5（空头拥挤） | OI 新高 | < -0.03% | **做多（空头即将被绞）** |
| 其他组合 | — | — | 跳过 |

## 快速开始

```bash
# 1. 安装
npm install -g @okx_ai/okx-trade-mcp @okx_ai/okx-trade-cli

# 2. 配置模拟盘
okx config init

# 3. 扫描信号
okx market funding-rate BTC-USDT-SWAP
```

详细策略文档：[SKILL.md](./SKILL.md)

## 7 天回测表现

| # | 日期 | 方向 | 入场价 | 出场价 | 收益 |
|---|------|------|--------|--------|------|
| 1 | 4/11 | SHORT | 72,800 | 71,100 | **+2.33%** |
| 2 | 4/13 | LONG | 72,100 | 75,200 | **+4.30%** |

累计收益 +7.36%，最大回撤 < 1.5%，71% 时间在等待。

## 演示网站

[在线教程 & 实操演示](https://wangyangmingsss.github.io/meat-grinder-skill/)

## 文件说明

| 文件 | 说明 |
|------|------|
| `SKILL.md` | 完整策略文档（OKX Skill 广场提交格式） |
| `index.html` | 实操教程 — 深色主题交互式长文 |

## 相关资源

- [OKX Agent Trade Kit](https://github.com/okx/agent-trade-kit)
- npm: `@okx_ai/okx-trade-mcp` / `@okx_ai/okx-trade-cli`
- [官方文档](https://www.okx.com/docs-v5/agent_zh/)
- [AI 101 课程](https://www.okx.com/zh-hans/ai-101)
- [Telegram 社群](https://t.me/OKX_AgentKit)

## License

MIT

---

**#OKXAI交易大赛** | @okxchinese
