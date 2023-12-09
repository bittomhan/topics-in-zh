---
description: 也涵盖堵塞无阻支付（Stuckless Payments）和冗余过度支付（Redundant Overpayments）
---

# 回旋支付 - Boomerang Payments

**冗余过度支付**是将 LN 支付分成多个部分的方法，其中支付方发送的金额和部分数量超过了支付接收方发票所需的金额。

即使由于转发失败导致一些部分未能在第一次尝试中到达接收方节点，其他足够多的部分可能到达，从而使接收方能够索取其开票金额。协议功能防止接收方索取超过开票金额的金额。与发送确切金额相比，最初过度支付可以在大多数情况下消除重新发送失败支付的延迟。

过度支付需要一种机制来防止接收方索取超过开票金额的金额。实现这一点的最简单机制是，支付方在接收方表示已收到哪些支付部分之前，不向接收方提供索取每个支付部分所需的所有信息。支付方随后可以仅发送索取开票金额所需部分数量的索取信息。这种方法的一个缺点是它需要在接收方和支付方之间进行额外的通信往返，这可能大致等同于处理一轮支付失败所需的时间。相比之下，确切的支付在最好的情况下会在第一次尝试时完成。这意味着这种类型的冗余过度支付在大多数情况下可以将最坏情况下的支付时间限制在一个较低的上限，但以大致加倍最佳情况下非过度支付所需时间的成本为代价。

其他机制可能能够使用密码学来消除往返通信的开销，使过度支付在与非过度支付相同的最佳情况时间内完成。然而，这种方法可能带来额外的复杂性，并且可能需要大量转发节点升级以支持新协议，才能广泛使用。

## 主要代码和文档

* [堵塞无阻支付](https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-June/002029.html)
* [回旋支付](https://arxiv.org/pdf/1910.01834.pdf)

## Optech 新闻简报和网站提及

**2023**

* [闪电网络开发者讨论支持冗余过度支付的协议更改](https://bitcoinops.org/en/newsletters/2023/07/26/#ptlcs-and-redundant-overpayment)
* [使用冗余过度支付代替服务质量标志](https://bitcoinops.org/en/newsletters/2023/02/22/#ln-quality-of-service-flag)

**2022**

* [使用算法和堵塞无阻支付加快支付传递](https://bitcoinops.org/en/newsletters/2022/03/23/#payment-delivery-algorithm-update)

**2021**

* [LN 峰会 2021：堵塞无阻支付](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)

**2020**

* [回旋支付演讲摘要](https://bitcoinops.org/en/newsletters/2020/02/26/#boomerang-redundancy-improves-latency-and-throughput-in-payment-channel-networks)

**2019**

* [提议了堵塞无阻支付](https://bitcoinops.org/en/newsletters/2019/07/03/#stuckless-payments)

## 参见

* [简化多路径支付（Simplified Multipath Payments）](https://bitcoinops.org/en/topics/multipath-payments/)
* [原子多路径支付（Atomic Multipath Payments）](https://bitcoinops.org/en/topics/atomic-multipath/)
