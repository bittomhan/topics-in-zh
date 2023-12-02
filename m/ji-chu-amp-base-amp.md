---
description: >-
  同时涵盖基础 AMP（Base AMP）、简化多路径支付（Simplified Multipath Payments）和多路径支付（Multipath
  Payments）
---

# 多部分支付 - Multipart Payments

**简化多路径支付（Simplified Multipath Payments, SMPs）** 也称为 **基础 AMP（Base AMP）**，是一种闪电网络（LN）支付，它将支付分割成两个或更多部分，所有部分共享相同的哈希原像（preimage），并且每个部分使用不同的路径发送。

尽管在原子多路径支付（[AMP](https://bitcoinops.org/en/topics/atomic-multipath/)）之后提出，但简化多路径支付在实现上需要对 LN 协议的更少更改，并且保留了支付者接收加密支付证明的能力，因此它们是首个在生产网络上部署的。

使用 [HTLCs](https://bitcoinops.org/en/topics/htlc/) 时，简化多路径支付的主要缺点是，第三方看到使用相同哈希的多个支付，可以推断出它们是更大真实支付的一部分。

AMP 和 SMP 都允许将高价值的 HTLCs 分割成多个更有可能单独成功的低价值 HTLCs，因此拥有足够流动性的支付者可以一次性使用几乎所有资金，无论这些资金跨越了多少个通道。

## 主要代码和文档

* [简化多路径支付](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-November/001577.html)

## Optech 新闻简报和网站提及

**2023 年**

* [动态支付切换和分割（PSS）被提议用于改善支付隐私](https://bitcoinops.org/en/newsletters/2023/10/04/#payment-splitting-and-switching)
* [LDK #2156 添加了对使用简化多路径支付的 keysend 支付的支持](https://bitcoinops.org/en/newsletters/2023/06/21/#ldk-2156)
* [关于使用多路径过度支付和恢复以减少支付延迟的讨论](https://bitcoinops.org/en/newsletters/2023/02/22/#ln-quality-of-service-flag)

**2022 年**

* [BOLTs #1031 允许在使用多路径时支付稍高于请求金额](https://bitcoinops.org/en/newsletters/2022/11/16/#bolts-1031)

**2021 年**

* [关于基础费用对多路径支付成本影响的讨论](https://bitcoinops.org/en/newsletters/2021/08/25/#zero-base-fee-ln-discussion)
* [Electrum 4.1.0 增加了对多路径支付的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#electrum-4-1-0-enhances-lightning-features)
* [新论文分析了多路径支付对路由成功的益处](https://bitcoinops.org/en/newsletters/2021/03/31/#paper-on-probabilistic-path-selection)

**2020 年**

* [Eclair #1599 改进了对直接通道对手的多路径支出](https://bitcoinops.org/en/newsletters/2020/11/18/#eclair-1599)
* [LND #4521 改进了多路径支付的发票路由提示](https://bitcoinops.org/en/newsletters/2020/08/19/#lnd-4521)
* [Zap 0.7.0 Beta 增加了对多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#zap-0-7-0-beta-released)
* [C-Lightning #3809 增加了发送多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#c-lightning-3809)
* [Eclair 0.4.1 增加了发送多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/07/08/#eclair-0-4-1)
* [Eclair #1427 和 #1439 为 Eclair 增加了发送多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/07/08/#eclair-1427)
* [Lightning Loop 增加了对多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/05/20/#lightning-loop-using-multipath-payments)
* [LND 0.10.0-beta 发布，支持多路径支付](https://bitcoinops.org/en/newsletters/2020/05/06/#lnd-0-10-0-beta)
* [LND 0.10 展示：多路径支付](https://bitcoinops.org/en/newsletters/2020/05/06/#lnd-v0-10)
* [Rust-Lightning #441 增加了对简化多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/04/22/#rust-lightning-441)
* [LND #3967 增加了发送多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/04/15/#lnd-3967)
* [LND #3970 将多路径支付添加到其支付生命周期中](https://bitcoinops.org/en/newsletters/2020/04/08/#lnd-3970)
* [Boomerang：使用多路径支付提高延迟和吞吐量](https://bitcoinops.org/en/newsletters/2020/02/26/#boomerang-redundancy-improves-latency-and-throughput-in-payment-channel-networks)
* [Eclair 0.3.3 增加了对多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/02/05/#upgrade-to-eclair-0-3-3)
* [LND 0.9.0-beta 增加了接收多路径支付的支持](https://bitcoinops.org/en/newsletters/2020/01/29/#upgrade-to-lnd-0-9-0-beta)
* [Eclair #1283 允许多路径支付穿越未公告通道](https://bitcoinops.org/en/newsletters/2020/01/22/#eclair-1283)

**2019 年**

* [2019 年度回顾：多路径支付](https://bitcoinops.org/en/newsletters/2019/12/28/#multipath)
* [多个 LN 实现增加了多路径支付支持](https://bitcoinops.org/en/newsletters/2019/12/18/#ln-implementations-add-multipath-payment-support)
* [LN 规范增加了基本多路径支付支持](https://bitcoinops.org/en/newsletters/2019/12/18/#bolts-643)
* [LND #3499 扩展了几个 RPC 以支持跟踪多路径支付](https://bitcoinops.org/en/newsletters/2019/11/27/#lnd-3499)
* [Eclair #1153 增加了对多路径支付的实验性支持](https://bitcoinops.org/en/newsletters/2019/11/20/#eclair-1153)
* [LND #3442 准备性 PR，增加了实现多路径支付所需的功能](https://bitcoinops.org/en/newsletters/2019/11/13/#lnd-3442)
* [LND #3390 将 HTLCs 与发票的跟踪分离，为 SMP 做准备](https://bitcoinops.org/en/newsletters/2019/09/11/#lnd-3390)

**2018 年**

* [LN 协议 1.1 目标：多路径支付](https://bitcoinops.org/en/newsletters/2018/11/20/#multi-path-payments)

## 参见

* [原子多路径支付（AMPs）](https://bitcoinops.org/en/topics/atomic-multipath/)
* [支付秘密](https://bitcoinops.org/en/topics/payment-secrets/)
