---
description: 同时涵盖提议（Offers）
---

# BOLT12

**提议**（Offers）是对闪电网络（LN）的一项拟议协议增强，它将允许节点通过 LN 请求和接收发票。

这一协议的一个常见用例是，商家生成二维码，顾客扫描二维码，顾客的 LN 节点将二维码中的一些细节（如订单 ID 号）通过 LN 发送给商家的节点，商家的节点返回发票（也通过 LN），发票显示给用户（用户同意支付），然后发送付款。

尽管上述用例今天已经通过 [BOLT11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md) 发票得到解决，但在尝试付款之前，支出和接收节点直接通信的能力提供了更多的灵活性。例如，可以用非比特币货币（例如美元）指定所请求的金额；如果自接收发票以来 BTC 至 USD 的汇率变化太大，两个节点可以自动协商更新可支付的 BTC 金额，使其再次与请求的 USD 金额一致。

节点之间的交互式通信还使得 BOLT11 的一次性使用哈希锁无法实现的功能成为可能，例如用于订阅和捐赠的重复付款。

## 主要代码和文档

* [BOLT12（草案）](https://github.com/rustyrussell/lightning-rfc/blob/guilt/offers/12-offer-encoding.md)

## Optech 新闻简报和网站提及

**2023**

* [为创建与提议兼容的闪电地址协议的想法](https://bitcoinops.org/en/newsletters/2023/11/22/#offers-compatible-ln-addresses)
* [Eclair #2752 允许提议引用节点使用短通道标识符（SCID）](https://bitcoinops.org/en/newsletters/2023/11/22/#eclair-2752)
* [LDK #2371 添加了管理使用提议的付款的支持](https://bitcoinops.org/en/newsletters/2023/09/20/#ldk-2371)
* [LDK #1977 允许序列化和反序列化提议](https://bitcoinops.org/en/newsletters/2023/03/01/#ldk-1977)
* [Eclair #2479 添加了支付提议的支持](https://bitcoinops.org/en/newsletters/2023/02/22/#eclair-2479)
* [Core Lightning #5892 更新了 CLN 对提议协议的实现](https://bitcoinops.org/en/newsletters/2023/02/08/#core-lightning-5892)
* [LDK #1738 和 #1908 提供了处理提议的额外功能](https://bitcoinops.org/en/newsletters/2023/01/04/#ldk-1738)

**2022**

* [Eclair #2499 允许在使用 BOLT12 提议时指定盲化路由](https://bitcoinops.org/en/newsletters/2022/11/30/#eclair-2499)
* [Core Lightning #5646 更新了提议的实现，移除了仅 x 公钥](https://bitcoinops.org/en/newsletters/2022/11/02/#core-lightning-5646)
* [Eclair #2416 添加了接收使用提议协议请求的付款的支持](https://bitcoinops.org/en/newsletters/2022/09/21/#eclair-2416)
* [Eclair #2117 添加了洋葱消息回复，为支持提议做准备](https://bitcoinops.org/en/newsletters/2022/01/12/#eclair-2117)

**2021**

* [2021 年度回顾：提议](https://bitcoinops.org/en/newsletters/2021/12/22/#offers)
* [LN 开发者大会总结，包括讨论提议](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [Spark Lightning Wallet 添加了对提议的部分支持](https://bitcoinops.org/en/newsletters/2021/08/18/#spark-lightning-wallet-adds-bolt12-support)
* [C-Lightning 0.10.1 更新了提议的实验性实现](https://bitcoinops.org/en/newsletters/2021/08/11/#c-lightning-0-10-1)
* [提议规范更新，不再要求签名](https://bitcoinops.org/en/newsletters/2021/07/14/#c-lightning-4625)
* [提议规范更新，部分解决支付堵塞问题](https://bitcoinops.org/en/newsletters/2021/04/21/#using-ln-offers-to-partly-address-stuck-payments)
* [C-Lightning 0.9.3 发布，支持提议的实验性支持](https://bitcoinops.org/en/newsletters/2021/01/27/#c-lightning-0-9-3)

**2020**

* [2020 年度回顾：LN 提议](https://bitcoinops.org/en/newsletters/2020/12/23/#ln-offers)
* [C-Lightning #4255 是提议系列 PR 中的第一个](https://bitcoinops.org/en/newsletters/2020/12/16/#c-lightning-4255)
* [新的直接消息协议用于提议](https://bitcoinops.org/en/newsletters/2020/02/26/#ln-direct-messages)

**2019**

* [新提议的 BOLT 用于提议协议](https://bitcoinops.org/en/newsletters/2019/11/13/#proposed-bolt-for-ln-offers)

## 参见

* [盲化路径（Blinded Paths）](https://bitcoinops.org/en/topics/rendez-vous-routing/)
