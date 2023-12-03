# 支付秘密 - Payment secrets

**支付秘密**是添加到 BOLT11 发票中的额外数据，支付者在其 BOLT4 洋葱加密支付中包含这些数据。这使得接收者只能接受来自预期支付者的支付，防止在使用简化多路径支付时对接收者的探测攻击。

_此主题描述是一个存根。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/payment-secrets.md) _提供有关该主题的更多背景信息。_

## 主要代码和文档

* [BOLT4](https://github.com/lightningnetwork/lightning-rfc/blob/master/04-onion-routing.md)
* [BOLT11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md)

## Optech 新闻简报和网站提及

**2023**

* [LDK #2156 增加了对多路径键发送支付的支持，这需要支付秘密](https://bitcoinops.org/en/newsletters/2023/06/21/#ldk-2156)

**2022**

* [Rust-Lightning #1177 使用支付秘密字段来存储加密的发票信息](https://bitcoinops.org/en/newsletters/2022/01/05/#rust-lightning-1177)

**2021**

* [BOLTs #887 更新 BOLT11，要求支付者指定支付秘密](https://bitcoinops.org/en/newsletters/2021/08/25/#bolts-887)
* [C-Lightning #4646 使支付秘密成为必需](https://bitcoinops.org/en/newsletters/2021/07/21/#c-lightning-4646)
* [LND #5336 允许通过更改支付秘密非交互式重用 AMP 发票](https://bitcoinops.org/en/newsletters/2021/06/09/#lnd-5336)
* [Eclair #1810 强制对等方表示并遵守支付秘密特性](https://bitcoinops.org/en/newsletters/2021/05/26/#eclair-1810)
* [Rust-Lightning #893 要求支付秘密以防止多路径探测](https://bitcoinops.org/en/newsletters/2021/05/05/#rust-lightning-893)

**2020**

* [LND #4752 阻止节点在没有支付秘密的情况下释放本地支付预图片](https://bitcoinops.org/en/newsletters/2020/12/02/#lnd-4752)
* [CVE-2020-26896 可以通过支付秘密来预防](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26896-improper-preimage-revelation)

**2019**

* [BOLTs #643 将支付秘密添加到闪电网络规范](https://bitcoinops.org/en/newsletters/2019/12/18/#bolts-643)
* [LND #3788 增加了对“支付地址”（支付秘密）的支持](https://bitcoinops.org/en/newsletters/2019/12/11/#lnd-3788)
* [C-Lightning #3259 增加了支付秘密以防止多路径探测](https://bitcoinops.org/en/newsletters/2019/12/04/#c-lightning-3259)

## 参见

* [简化多路径支付](https://bitcoinops.org/en/topics/multipath-payments/)
