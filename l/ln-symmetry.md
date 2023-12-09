---
description: 也涵盖 Eltoo
---

# LN-Symmetry

**Eltoo**（也被称为 **LN-Symmetry**）是一个提议的闪电网络（LN）执行层，它允许任何后来的通道状态替换任何早期的通道状态。尽管 eltoo 可以与现有 LN 通道中使用的类似处罚机制一起使用，但 eltoo 不需要处罚机制就能保证安全。

如果没有使用处罚机制的 eltoo，发布旧状态没有任何危害，除了需要支付交易费用。这使得在突发故障或其他问题后尝试从备份中恢复 LN 节点变得不那么危险。它还使三个或更多方一起开设单个 LN 通道变得更加简单，使得如[通道工厂（channel factories）](https://bitcoinops.org/en/topics/channel-factories/) 等特性成为可能。

LN 通道没有处罚的另一个后果是，使用 eltoo 的 LN 节点只需要存储最新的状态。对于那些缺乏大量持久存储的设备（例如，硬件钱包），它们可能无法存储足够的数据来有效使用基于处罚的 LN——但只要它们能存储几 kB 的数据，就应该能够使用基于 eltoo 的 LN。

## 主要代码和文档

* [Eltoo](https://blockstream.com/eltoo.pdf)

## Optech 新闻简报和网站提及

**2023**

* [使用与 eltoo 兼容的契约改进 LN 的可扩展性](https://bitcoinops.org/en/newsletters/2023/09/27/#using-covenants-to-improve-ln-scalability)
* [关于 LN-symmetry 中附录字段使用的讨论](https://bitcoinops.org/en/newsletters/2023/06/14/#discussion-about-the-taproot-annex)

**2022**

* [使用交易内省防止 eltoo 通道中的固定攻击](https://bitcoinops.org/en/newsletters/2022/05/18/#using-transaction-introspection-to-prevent-rbf-pinning)

**2021**

* [LN 开发者会议总结，包括对 eltoo 的讨论](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [LN PTLC 提案提供了一些与 eltoo 相同的好处，无需软分叉](https://bitcoinops.org/en/newsletters/2021/10/13/#multiple-proposed-ln-improvements)
* [继承标识符提案，提出了与 eltoo 不同的通道承诺机制](https://bitcoinops.org/en/newsletters/2021/10/06/#proposal-for-transaction-heritage-identifiers)
* [Eltoo 演示实现及新博客文章概述](https://bitcoinops.org/en/newsletters/2021/09/01/#eltoo-example-channel)

**2020**

* [使用交易固定和选择性中继等攻击对 eltoo 的影响](https://bitcoinops.org/en/newsletters/2020/08/12/#discussion-about-eltoo-and-sighash-anyprevout)
* [升级 LN 承诺格式，包括 eltoo](https://bitcoinops.org/en/newsletters/2020/07/29/#upgrading-channel-commitment-formats)
* [SIGHASH\_NOINPUT 和 eltoo 对 LN 备份的影响](https://bitcoinops.org/en/newsletters/2020/06/03/#ln-backups)
* [在没有 eltoo 的情况下实现状态链](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)- [`SIGHASH_ANYPREVOUTANYSCRIPT` 的修改，以提高 eltoo 的灵活性](https://bitcoinops.org/en/newsletters/2020/01/29/#layered-commitments-with-eltoo)

**2019**

* [Eltoo 演示实现](https://bitcoinops.org/en/newsletters/2019/09/11/#eltoo-sample-implementation-and-discussion)
* [与 Eltoo 兼容的 SIGHASH\_ANYPREVOUT 提案](https://bitcoinops.org/en/newsletters/2019/05/21/#proposed-anyprevout-sighash-modes)
* [基于 Eltoo 的支付通道的优化](https://bitcoinops.org/en/newsletters/2019/01/08/#continued-sighash-discussion)

**2018**

* [2018 年回顾：Eltoo](https://bitcoinops.org/en/newsletters/2018/12/28#april)

## 参见

* [SIGHASH\_ANYPREVOUT](https://bitcoinops.org/en/topics/sighash\_anyprevout/)
