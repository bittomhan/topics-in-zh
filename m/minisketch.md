---
description: 同时涵盖 Libminisketch
---

# Minisketch

**Minisketch** 是一个实现了一种算法的库，该算法允许在八卦协议（gossip protocols）中高效地进行集合协调（set reconciliation），例如在比特币和 LN（闪电网络）中使用的协议。

Minisketch 提供的集合协调类型是所提议的 [Erlay](https://bitcoinops.org/en/topics/erlay/) 改进比特币交易中继效率的基础。

Minisketch 不应与 [miniscript](https://bitcoinops.org/en/topics/miniscript/) 混淆，后者是一个帮助钱包创建和实现比特币安全策略的系统。

## 主要代码和文档

* [libminisketch](https://github.com/sipa/minisketch)

## Optech 新闻简报和网站提及

**2022**

* [对 LN 速率限制和 minisketch 八卦传播的互动进行研究](https://bitcoinops.org/en/newsletters/2022/05/04/#ln-gossip-rate-limiting)
* [为使用 minisketch 而设计的新 LN 八卦线协议提案](https://bitcoinops.org/en/newsletters/2022/02/23/#updated-ln-gossip-proposal)

**2018**

* [2018 年回顾：减少交易中继数据的研究](https://bitcoinops.org/en/newsletters/2018/12/28/#libminisketch)
* [发布 Minisketch 库，对比特币和 LN 具有影响](https://bitcoinops.org/en/newsletters/2018/12/18/#minisketch-library-released)
* [研究用于交易的带宽高效集合协调协议](https://bitcoinops.org/en/newsletters/2018/08/21/#bandwidth-efficient-set-reconciliation-protocol-for-transactions)

## 参见

* [Erlay](https://bitcoinops.org/en/topics/erlay/)
