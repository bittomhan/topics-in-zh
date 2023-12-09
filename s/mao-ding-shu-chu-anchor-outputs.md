---
description: 也涵盖锚定输出（Anchor Outputs）
---

# 简化承诺 - Simplified Commitments

**锚定输出** 是闪电网络（LN）承诺交易中的特殊输出，设计目的是允许对交易进行费用提升。这个提案的早期名称是**简化承诺（Simplified Commitments）**。

每次LN通道中的余额发生变化时，就会创建并由参与方签署一个_承诺交易（commitment transaction）_。只有当一方决定单方面关闭通道时（例如，因为另一方无响应），才会广播该交易。由于承诺交易的广播可能发生在创建后很长时间，所以承诺交易可能会支付过多或过少的交易费用。支付过低的费率可能会阻止承诺交易在其中包含的任何时间锁定（timelocks）到期前确认，从而导致资金被盗取。

解决方案是让承诺交易支付最低额度的费用，然后允许任一通道参与方对交易进行费用提升。早期使用[替换费用提升（Replace-by-Fee, RBF）](https://bitcoinops.org/en/topics/replace-by-fee/)策略的设计遇到了[交易钉扎（Transaction Pinning）](https://bitcoinops.org/en/topics/transaction-pinning/)的问题。后续设计使用[子支付父（Child Pays For Parent, CPFP）](https://bitcoinops.org/en/topics/cpfp/)费用提升策略，并依赖于[CPFP carve-out](https://bitcoinops.org/en/topics/cpfp-carve-out/)来规避钉扎问题。

截至目前，最新的设计方案在承诺交易中为每个LN方添加了两个输出，并要求承诺交易中的所有其他输出的脚本都被`1 OP_CHECKSEQUENCEVERIFY`（CSV）条件所束缚，防止它们在至少一个区块内被花费。

为了充分发挥效果，该协议还依赖于比特币全节点实现[打包转发（Package Relay）](https://bitcoinops.org/en/topics/package-relay/)，以便在交易费率低于节点的最低转发费用时，仍有办法使用CPFP对承诺交易进行费用提升。但在打包转发可用之前，LN节点可以为他们的承诺交易支付稍高的费率，以确保它们被节点接受。

## 主要代码与文档

* [锚定输出](https://github.com/lightningnetwork/lightning-rfc/pull/688)
* [零HTLC费用锚定输出](https://github.com/lightningnetwork/lightning-rfc/pull/824)

## Optech 新闻稿和网站提及

**2023**

* [Core Lightning #6334 更新并扩展了CLN对锚定输出的实验性支持](https://bitcoinops.org/en/newsletters/2023/07/05/#core-lightning-6334)
* [LDK #2368 允许手动接受使用锚定输出创建的新通道](https://bitcoinops.org/en/newsletters/2023/06/28/#ldk-2368)
* [LDK #1841 实现了BOLTs #824中描述的费用窃取攻击的解决方案](https://bitcoinops.org/en/newsletters/2023/05/24/#ldk-1841)
* [LDK #1860 添加了对使用锚定输出的通道的支持](https://bitcoinops.org/en/newsletters/2023/02/01/#ldk-1860)

**2022**

* [在v3交易上构建的临时锚点实现](https://bitcoinops.org/en/newsletters/2022/12/07/#ephemeral-anchors-implementation)
* [提议使用多个预先承诺的费用以避免在许多情况下需要锚定输出](https://bitcoinops.org/en/newsletters/2022/11/02/#anchor-outputs-workaround)
* [提议转发v3交易以改进锚定输出](https://bitcoinops.org/en/newsletters/2022/10/05/#proposed-new-transaction-relay-policies-designed-for-ln-penalty)
* [Eclair #2134 默认启用锚定输出](https://bitcoinops.org/en/newsletters/2022/01/26/#eclair-2134)

**2021**

* [Rust-Lightning #1176 添加了对锚定输出风格费用提升的初始支持](https://bitcoinops.org/en/newsletters/2021/12/01/#rust-lightning-1176)
* [在零HTLC费用锚定输出协议中恢复HD钱包存在的复杂性](https://bitcoinops.org/en/newsletters/2021/09/29/#challenges-recovering-ln-close-transactions-using-only-a-seed)
* [Eclair #1932 实现了零HTLC费用锚定输出协议](https://bitcoinops.org/en/newsletters/2021/09/22/#eclair-1932)
* [BOLTs #824 添加了一种锚定输出协议的变体，以防止费用窃取攻击](https://bitcoinops.org/en/newsletters/2021/09/08/#bolts-824)
* [LND 0.13.0-beta 开始默认在所有新通道中使用锚定输出](https://bitcoinops.org/en/newsletters/2021/06/23/#lnd-0-13-0-beta)
* [LND #5274 限制了为费用提升锚定输出保留的最大资金](https://bitcoinops.org/en/newsletters/2021/05/19/#lnd-5274)
* [就在LND中默认使用锚定输出征求反馈](https://bitcoinops.org/en/newsletters/2021/04/21/#using-anchor-outputs-by-default-in-lnd)
* [Eclair 0.5.1 添加和更新了准备使用锚定输出的功能](https://bitcoinops.org/en/newsletters/2021/03/10/#eclair-0-5-1)
* [LND 0.12.0-beta 为使用锚定输出的通道添加了守望塔支持](https://bitcoinops.org/en/newsletters/2021/01/27/#lnd-0-12-0-beta)
* [LND #4908 为使用锚定输出时保留费用提升余额](https://bitcoinops.org/en/newsletters/2021/01/27/#lnd-4908)

**2020**

* [2020年度回顾：锚定输出](https://bitcoinops.org/en/newsletters/2020/12/23/#anchor-outputs)
* [LND #4779 允许从锚定输出中扫清HTLCs](https://bitcoinops.org/en/newsletters/2020/12/16/#lnd-4779)
* [BOLT5 更新以防止针对锚定输出的钉扎攻击](https://bitcoinops.org/en/newsletters/2020/12/16/#bolts-803)
* [LND #4782 为使用锚定输出的通道添加了守望塔客户端支持](https://bitcoinops.org/en/newsletters/2020/12/09/#lnd-4782)
* [Eclair 0.4.2 添加了对锚定输出的实验性支持](https://bitcoinops.org/en/newsletters/2020/10/14/#eclair-0-4-2)
* [为什么锚定输出需要强制执行 nSequence 为 1？](https://bitcoinops.org/en/newsletters/2020/09/30/#why-do-anchor-outputs-need-to-enforce-an-nsequence-of-1)
* [LND #4576 开始为LND的守望塔添加锚定输出支持](https://bitcoinops.org/en/newsletters/2020/09/30/#lnd-4576)
* [Eclair #1501 添加了对单方关闭使用锚点的通道的支持](https://bitcoinops.org/en/newsletters/2020/09/30/#eclair-1501)
* [LND #4606 & #4592 提高了LND对锚定输出费用提升的有效性](https://bitcoinops.org/en/newsletters/2020/09/23/#lnd-4606)
* [LND #4558 将LND更新到最新的锚定输出规范](https://bitcoinops.org/en/newsletters/2020/09/16/#lnd-4558)
* [BOLTs #688 将锚定输出支持添加到LN协议中](https://bitcoinops.org/en/newsletters/2020/08/26/#bolts-688)
* [C-Lightning #3830 添加了对锚定输出的实验性支持](https://bitcoinops.org/en/newsletters/2020/08/19/#c-lightning-3830)
* [Eclair #1491 添加了对锚定输出的支持](https://bitcoinops.org/en/newsletters/2020/08/05/#eclair-1491)
* [讨论解决LN攻击的方案，包括锚定输出](https://bitcoinops.org/en/newsletters/2020/08/05/#chicago-meetup-discussion)
* [Eclair #1484 添加了对锚定输出的基本支持](https://bitcoinops.org/en/newsletters/2020/07/29/#eclair-1484)
* [锚定输出可能有助于减轻LN费用勒索攻击](https://bitcoinops.org/en/newsletters/2020/06/24/#ln-fee-ransom-attack)
* [LND 0.10演讲：锚定输出](https://bitcoinops.org/en/newsletters/2020/05/06/#lnd-v0-10)
* [使用锚定输出确保HTLC发送可进行费用提升](https://bitcoinops.org/en/newsletters/2020/04/29/#settlement-transaction-anchor-outputs)
* [LND #3821 添加了草案锚定承诺支持](https://bitcoinops.org/en/newsletters/2020/03/18/#lnd-3821)
* [LND #3829 更新代码和文档以简化添加锚定输出](https://bitcoinops.org/en/newsletters/2020/01/15/#lnd-3829)

**2019**

* [2019年度回顾：锚定输出](https://bitcoinops.org/en/newsletters/2019/12/28/#anchor-outputs)
* [继续讨论LN锚定输出](https://bitcoinops.org/en/newsletters/2019/11/06/#continued-discussion-of-ln-anchor-outputs)
* [LN简化承诺讨论](https://bitcoinops.org/en/newsletters/2019/10/30/#ln-simplified-commitments)

**2018**

* [LN简化费用提升](https://bitcoinops.org/en/newsletters/2018/11/27/#simplified-fee-bumping-for-ln)

## 参见

* [CPFP carve-out](https://bitcoinops.org/en/topics/cpfp-carve-out/)
* [打包转发（Package Relay）](https://bitcoinops.org/en/topics/package-relay/)
* [临时锚点（Ephemeral Anchors）](https://bitcoinops.org/en/topics/ephemeral-anchors/)
