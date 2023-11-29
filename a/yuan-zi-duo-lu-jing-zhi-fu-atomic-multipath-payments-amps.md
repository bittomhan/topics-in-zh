---
description: 同时涵盖 AMP
---

# 原子多路径支付（Atomic Multipath Payments, AMPs）

**原子多路径支付（Atomic Multipath Payments, AMPs）**，有时被称为**原始AMP（Original AMP）或OG AMP**，允许支付者支付多个从同一前置（preimage）派生的哈希值——这是接收者只有在收到足够数量的份额时才能重建的前置。

与简化多路径支付（[SMP](https://bitcoinops.org/en/topics/multipath-payments/)）不同，AMP 仅允许接收者在收到所有个别部分时接受支付。每个使用不同哈希的份额通过防止第三方自动将分开的支付关联起来，增加了隐私。该提案的缺点是支付者选择所有前置，因此对前置的了解并不提供他们实际向接收者支付的密码学证明。

AMP 和 SMP 都允许将较高价值的HTLCs（Hash Time-Locked Contracts）分割成多个较低价值的HTLCs，这些HTLCs 更有可能单独成功，因此拥有足够流动性的支付者可以同时使用几乎所有资金，无论这些资金分布在多少个通道中。

## 主要代码与文档

* [原子多路径支付](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-February/000993.html)

## Optech 新闻稿和网站提及

**2021年**

* [2021年度回顾：原子多路径支付](https://bitcoinops.org/en/newsletters/2021/12/22/#amp)
* [LND 0.14.0-beta 允许对同一AMP发票进行多次自发支付](https://bitcoinops.org/en/newsletters/2021/11/24/#lnd-0-14-0-beta)
* [LND #5803 允许对同一AMP发票进行多次自发支付](https://bitcoinops.org/en/newsletters/2021/11/03/#lnd-5803)
* [LND 0.13.0-beta 允许接收和发送使用AMP的支付](https://bitcoinops.org/en/newsletters/2021/06/23/#lnd-0-13-0-beta)
* [LND #5336 添加了用户非交互式重复使用AMP发票的能力](https://bitcoinops.org/en/newsletters/2021/06/09/#lnd-5336)
* [LND #5253 添加了对原子多路径支付（AMP）发票的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#lnd-5253)
* [LND #5159 添加了进行自发AMP的支持](https://bitcoinops.org/en/newsletters/2021/05/05/#lnd-5159)
* [LND #5108 添加了使用AMP进行自发多路径支付的支持](https://bitcoinops.org/en/newsletters/2021/04/14/#lnd-5108)

**2020年**

* [LND #3957 添加了有用于支持原子多路径支付（AMP）的代码](https://bitcoinops.org/en/newsletters/2020/02/12/#lnd-3957)

**2018年**

* [闪电网络协议1.1目标：多路径支付](https://bitcoinops.org/en/newsletters/2018/11/20/#multi-path-payments)

## 参见

* [简化多路径支付（Simplified Multipath Payments, SMP）](https://bitcoinops.org/en/topics/multipath-payments/)
