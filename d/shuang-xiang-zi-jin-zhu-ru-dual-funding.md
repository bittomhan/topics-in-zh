---
description: 也涵盖互动式资金协议（Interactive funding protocol）
---

# 双向资金注入 - Dual funding

**双向资金注入** 指的是为闪电网络（LN）创建一个支付通道，其中双方都可以贡献资金。这一协议，被称为_第二版通道建立协议（version 2 channel establishment protocol）_，也可以用于协商开设单向资金通道，但其主要目的是为双向资金注入提供支持。

对 LN 的[早期分析](https://docs.google.com/presentation/d/1G4xchDGcO37DJ2lPC\_XYyZIUkJc2khnLrCaZXgvDN0U/edit?pref=2\&pli=1#slide=id.g85f425098\_0\_2)表明，建设一个由请求打开支付通道的用户提供所有资金并支付所有链上费用的软件会更简单，这被称为_单向资金通道（single funded channels）_。这样可以防止攻击者免费或廉价地开设新通道，锁定对手方的资金，然后让受害者支付链上费用以取回他们的钱。

对于支出者来说，单向资金通道工作得很好。一旦通道开通，用户就可以开始使用 LN 的所有速度、效率和隐私优势进行消费。但是，新开通的单向资金通道的接收者在花费资金之前无法使用它来接收资金。这对希望通过 LN 接受支付但尚未准备通过 LN 支付相等金额费用的商家来说是个问题。

解决这个问题的一个方法是允许通道进行双向资金注入，一旦通道开通，立即允许双向消费。双向资金通道不需要在双方开始时拥有相同金额的资金，所以希望能够接收大量比特币的商家可能只需要贡献通道总容量的一小部分。

双向资金协议也可用于开通新的单向资金通道。当参与方希望使用协议的能力来沟通节点偏好并找到各种通道参数的相互可接受的值时，这可能具有优势。

在双向资金注入可用后，它可能与新提出的 [节点公告](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-November/001532.html) 结合使用，这有助于买卖入站容量的双方以去中心化的方式找到对方。

双向资金注入确实要求每一方向对方展示他们拥有的一个 UTXO。像其他需要此类操作的协议（如 [coinjoin](https://bitcoinops.org/en/topics/coinjoin/) 和 [payjoin](https://bitcoinops.org/en/topics/payjoin/)），这可以被攻击者利用来了解谁拥有哪个 UTXO。已经讨论了几种 [方法](https://bitcoinops.org/en/newsletters/2020/02/05/#podle) 来[限制](https://bitcoinops.org/en/newsletters/2020/02/19/#using-podle-in-ln)这个[问题](https://bitcoinops.org/en/newsletters/2021/01/13/#ln-dual-funding-anti-utxo-probing)。

## 主要代码和文档

* [双向资金注入（Dual funding）](https://github.com/lightningnetwork/lightning-rfc/pull/851)

## Optech 新闻简报和网站提及

**2023**

* [Core Lightning #6824 更新了互动式资金协议的实现](https://bitcoinops.org/en/newsletters/2023/11/08/#core-lightning-6824)
* [LDK #2077 重构代码，以便更容易地添加对双向资金通道的支持](https://bitcoinops.org/en/newsletters/2023/06/28/#ldk-2077)
* [LDK #1794 开始添加对双向资金的支持](https://bitcoinops.org/en/newsletters/2023/05/17/#ldk-1794)
* [在双向资金注入时对零确认通道的挑战](https://bitcoinops.org/en/newsletters/2023/05/17/#challenges-with-zero-conf-channels-when-dual-funding)
* [Eclair #2596 限制了双向资金通道开放中的 RBF（Replace-By-Fee）费用增加次数](https://bitcoinops.org/en/newsletters/2023/02/22/#eclair-2596)
* [Core Lightning #5670 和 #5956 对双向资金的实现进行了各种更新](https://bitcoinops.org/en/newsletters/2023/02/15/#core-lightning-5670)

**2022**

* [2022 年回顾：互动式和双向资金注入](https://bitcoinops.org/en/newsletters/2022/12/21/#dual-funding)
* [Eclair #2463 和 #2461 增强了 RBF 费用增加互动式资金的稳健性](https://bitcoinops.org/en/newsletters/2022/10/26/#eclair-2463)
* [Eclair #2406 允许在互动式资金协议中要求确认的输入](https://bitcoinops.org/en/newsletters/2022/09/14/#eclair-2406)
* [Eclair #2275 完成了对双向资金协议的实验性支持](https://bitcoinops.org/en/newsletters/2022/08/31/#eclair-2275)
* [Eclair #2273 实现了建议的互动式资金协议](https://bitcoinops.org/en/newsletters/2022/08/17/#eclair-2273)

**2021**

* [2021 年回顾：流动性广告](https://bitcoinops.org/en/newsletters/2021/12/22/#liq-ads)
* [2021 年回顾：双向资金通道](https://bitcoinops.org/en/newsletters/2021/12/22/#dual-funding)
* [C-Lightning 0.10.1 更新了双向资金的实验性实现](https://bitcoinops.org/en/newsletters/2021/08/11/#c-lightning-0-10-1)
* [C-Lightning #4639 添加了基于双向资金的流动性广告的实验性支持](https://bitcoinops.org/en/newsletters/2021/07/28/#c-lightning-4639)
* [C-Lightning #4489 添加了配置双向资金行为的插件](https://bitcoinops.org/en/newsletters/2021/05/12/#c-lightning-4489)
* [双向资金的互动式构建用于割接提案](https://bitcoinops.org/en/newsletters/2021/04/28/#draft-specification-for-ln-splicing)
* [C-Lightning 0.10.0 包括双向资金的实验性支持](https://bitcoinops.org/en/newsletters/2021/04/07/#c-lightning-0-10-0)- [C-Lightning #4410 更新了双向资金的实验性实现](https://bitcoinops.org/en/newsletters/2021/03/17/#c-lightning-4410)
* [在双向资金通道中防止 UTXO 探测；PoDLE 权衡](https://bitcoinops.org/en/newsletters/2021/01/13/#ln-dual-funding-anti-utxo-probing)

**2020**

* [2020 年回顾：闪电网络的双向资金和互动式资金](https://bitcoinops.org/en/newsletters/2020/12/23/#dual-interactive-funding)
* [C-Lightning #3973 添加了双向资金通道的接收方](https://bitcoinops.org/en/newsletters/2020/09/16/#c-lightning-3973)
* [C-Lightning #3954 为双向资金的 PSBT RPC 添加了锁定时间支持](https://bitcoinops.org/en/newsletters/2020/08/26/#c-lightning-3954)
* [悉尼聚会讨论闪电网络，包括双向资金](https://bitcoinops.org/en/newsletters/2020/06/03/#sydney-meetup-discussion)
* [C-Lightning #3738 添加了对 PSBT 的初始支持，作为双向资金的一部分](https://bitcoinops.org/en/newsletters/2020/05/27/#c-lightning-3738)
* [在闪电网络中使用 PoDLE 进行双向资金的隐私保护](https://bitcoinops.org/en/newsletters/2020/02/19/#using-podle-in-ln)
* [资金交易的互动式构建](https://bitcoinops.org/en/newsletters/2020/02/05/#interactive-construction-of-ln-funding-transactions)

**2018**

* [闪电网络协议 1.1 版本目标：双向资金](https://bitcoinops.org/en/newsletters/2018/11/20/#dual-funded-channels)

## 参见

* [流动性广告（Liquidity advertisements）](https://bitcoinops.org/en/topics/liquidity-advertisements/)
* [PSBT（双向资金的依赖项）](https://bitcoinops.org/en/topics/psbt/)
* [潜艇交换（Submarine swaps）](https://bitcoinops.org/en/topics/submarine-swaps/)
* [割接（Splicing）](https://bitcoinops.org/en/topics/splicing/)
