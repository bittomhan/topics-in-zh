---
description: 同时涵盖 Keysend
---

# 自发支付  - Spontaneous payments

**自发支付**是指一个 LN（闪电网络）节点无需先接收到发票即可支付给另一个节点的能力。截至 2022 年，这通常是通过使用 **keysend** 支付来实现的。

用于常规 LN 支付的发票包含了支付者和每个路由节点作为哈希时间锁合约（Hash-Time-Locked-Contract）一部分所使用的哈希。自发支付需要复制这种安全机制，但无需发票机制进行通信。

截至 2022 年，常用的方法是 [keysend](https://github.com/lightning/blips/blob/master/blip-0003.md)：支付者选择一个哈希原像（pre-image），将其加密到接收者的密钥，然后作为额外数据附加在路由数据包中。当付款到达接收方时，他们可以解密数据并使用预映像来领取付款。2022 年，几个流行的 LN 节点添加了对 keysend 的支持。

2019 年提出了一种替代机制，但尚未见到广泛实施或使用：发送支付的人将他们的密钥和接收者的密钥结合起来，创建一个共享秘密。然后，花费者使用这个秘密的哈希作为预映像。接收者也可以生成共享秘密，并使用它来接受付款。

## 主要代码和文档

* [BLIP3: Keysend 支付](https://github.com/lightning/blips/blob/master/blip-0003.md)

## Optech 新闻简报和网站提及

**2023**

* [LDK #2156 增加对使用简化多路径支付的 keysend 支付的支持](https://bitcoinops.org/en/newsletters/2023/06/21/#ldk-2156)
* [LDK #2002 增加对自动重新发送自发支付的支持](https://bitcoinops.org/en/newsletters/2023/02/15/#ldk-2002)
* [Eclair #2573 开始接受不包含支付秘密的 keysend 支付](https://bitcoinops.org/en/newsletters/2023/02/01/#eclair-2573)

**2022**

* [LND #5414 开始宣传对先前实现的 keysend 支付的支持](https://bitcoinops.org/en/newsletters/2022/04/27/#lnd-6414)

**2021**

* [LND #5803 允许对同一发票进行多次自发支付](https://bitcoinops.org/en/newsletters/2021/11/03/#lnd-5803)
* [Rust-Lightning #967 添加对发送 keysend 风格自发支付的支持](https://bitcoinops.org/en/newsletters/2021/08/04/#rust-lightning-967)
* [LND #5108 添加对使用 AMP 进行自发多路径支付的支持](https://bitcoinops.org/en/newsletters/2021/04/14/#lnd-5108)
* [C-Lightning #4404 允许向不宣传支持的节点 keysending](https://bitcoinops.org/en/newsletters/2021/03/17/#c-lightning-4404)

**2020**

* [Eclair 0.4.2 增加对 keysend 风格自发支付的支持](https://bitcoinops.org/en/newsletters/2020/10/14/#eclair-0-4-2)
* [Eclair #1485 增加对 keysend 自发支付的支持](https://bitcoinops.org/en/newsletters/2020/07/29/#eclair-1485)
* [Zap 0.7.0 Beta 增加对自发支付的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#zap-0-7-0-beta-released)
* [C-Lightning #3792 增加对发送 keysend 自发支付的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#c-lightning-3792)
* [LND #4167 允许使用 keysend 进行的自发支付被保留](https://bitcoinops.org/en/newsletters/2020/07/08/#lnd-4167)
* [Juggernaut 使用自发支付进行消息传递和即时支付](https://bitcoinops.org/en/newsletters/2020/05/20/#lightning-based-messenger-application-juggernaut-launches)
* [Breez 钱包增加对自发支付的支持](https://bitcoinops.org/en/newsletters/2020/05/20/#breez-wallet-enables-spontaneous-payments)
* [C-Lightning 0.8.2 发布，包含一个发送自发支付的插件](https://bitcoinops.org/en/newsletters/2020/05/06/#c-lightning-0-8-2)
* [C-Lightning #3611 增加一个 keysend 插件以支持自发支付](https://bitcoinops.org/en/newsletters/2020/04/22/#c-lightning-3611)
* [Eclair 0.3.3 增加对蹦床支付的实验性支持](https://bitcoinops.org/en/newsletters/2020/02/05/#upgrade-to-eclair-0-3-3)

**2019**

* [使用 ECDH 进行非协调 LN 支付](https://bitcoinops.org/en/newsletters/2019/06/19/#using-ecdh-for-uncoordinated-ln-payments)
* [LND PR 为自发 LN 支付](https://bitcoinops.org/en/newsletters/2019/01/22/#pr-opened-for-spontaneous-ln-payments)
