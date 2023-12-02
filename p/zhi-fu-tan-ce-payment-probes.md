---
description: 也涵盖探测（Probing）
---

# 支付探测 - Payment probes

**支付探测（Payment probes）**是设计用来发现它们经过的闪电网络（LN）通道的信息的数据包，例如通道当前是否能够处理某个大小的支付，或者每个参与者在通道中分配了多少比特币。探测使用常规支付（HTLC）机制，但设计上始终会失败，从而防止任何资金转移。探测可能有用，但也可能降低用户隐私。

_此主题描述是一个存根。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/payment-probes.md) _提供有关该主题的更多背景信息。_

## Optech 新闻简报和网站提及

**2023**

* [提出动态支付切换和拆分（PSS）来阻止余额发现攻击](https://bitcoinops.org/en/newsletters/2023/10/04/#payment-splitting-and-switching)
* [LDK #2534 增加了对预支付探测的支持](https://bitcoinops.org/en/newsletters/2023/09/27/#ldk-2534)

**2022**

* [LDK #1567 为基本支付探测 API 增加了支持](https://bitcoinops.org/en/newsletters/2022/07/13/#ldk-1567)
* [LDK #1555 现在略微倾向于通过使平衡探测更难的通道进行支付](https://bitcoinops.org/en/newsletters/2022/07/06/#ldk-1555)
* [闪电网络开发者会议总结：探测和余额共享](https://bitcoinops.org/en/newsletters/2022/06/15/#probing-and-balance-sharing)

**2021**

* [降低探测成本以使攻击更昂贵](https://bitcoinops.org/en/newsletters/2021/10/20/#lowering-the-cost-of-probing-to-make-attacks-more-expensive)
* [在双资金通道中防止 UTXO 探测](https://bitcoinops.org/en/newsletters/2021/01/13/#ln-dual-funding-anti-utxo-probing)

**2020**

* [关于预付费用的讨论及其提高探测成本的能力](https://bitcoinops.org/en/newsletters/2020/10/21/#more-ln-upfront-fees-discussion)
* [关于在互动式构建的闪电网络资金交易中防止 UTXO 探测的讨论](https://bitcoinops.org/en/newsletters/2020/02/05/#interactive-construction-of-ln-funding-transactions)

**2019**

* [C-Lightning #3259 增加了对旨在抵抗接收者探测的支付秘密的支持](https://bitcoinops.org/en/newsletters/2019/12/04/#c-lightning-3259)
* [BOLTs #608 为 BOLT4 提供了隐私更新，以探测通道的最终接收者](https://bitcoinops.org/en/newsletters/2019/08/28/#bolts-608)
* [Eclair](https://bitcoinops.org/en/newsletters/2019/01/22/#eclair-762)

**2018**

* [使路径探测更方便](https://bitcoinops.org/en/newsletters/2018/11/13/#making-path-probing-more-convenient)

## 参见

* [即时交付（JIT）路由](https://bitcoinops.org/en/topics/jit-routing/)
* [通道堵塞攻击](https://bitcoinops.org/en/topics/channel-jamming-attacks/)
