---
description: 也涵盖 Wumbo
---

# 大容量通道  - Large channels

**大容量通道**是指双方节点发送 `option_support_large_channel` 参数的 LN（闪电网络）支付通道，这种通道可以用超过 0.16777216 BTC 的余额来资助。

在 LN 的早期发展阶段，开发者们 [达成了共识](https://medium.com/@rusty\_lightning/bitcoin-lightning-faq-why-the-0-042-bitcoin-limit-2eb48b703f3)，暂时将通道的最大大小限制在 224 个基本单位以下（0.16777216 BTC；当时约 40 美元）和单笔支付限制在 232 msat（0.04294967296 BTC；当时约 10 美元）。目的是限制任何个体早期采用者由于软件中的漏洞而可能遭受的损失：

> 我保证，早期版本的闪电客户端会有漏洞，人们会因此失去钱。\[…] 知道如果你因为我的漏洞失去了钱，我可以请你喝杯咖啡或啤酒来交换你的故事，我们差不多就扯平了。 —LN 开发者 Rusty Russell（原文强调）

经过数年的 LN 发展，[2018 年 LN 规范会议](https://bitcoinops.org/en/newsletters/2018/11/20/#feature-news-lightning-network-protocol-11-goals) 决定允许实现选择加入 [wumbo](https://bitcoinops.org/en/newsletters/2018/11/20/#wumbo)（巨大）通道大小，没有协议级别的金额限制，尽管实现和用户仍可以拒绝接受超过可自定义大小的通道。这一新功能的支持，后来被命名为 `option_support_large_channel`，在 2020 年在 LN 软件中得到了广泛的实现。

每笔支付大约 0.04 BTC 的限制仍然是 LN 协议规范的一部分，但 [多路径支付](https://bitcoinops.org/en/topics/multipath-payments/) 允许将超过限制的支付金额分割成几个小部分，每个部分都低于限制，从而使任何兼容的软件都可以选择性地发送或接收超过限制的支付。

## 主要代码和文档

* [更新 BOLT 规范，添加对大容量通道的可选支持](https://github.com/lightningnetwork/lightning-rfc/pull/596)

## Optech 新闻简报和网站提及

**2023**

* [Core Lightning #6783 弃用大容量通道的配置选项，使其始终启用](https://bitcoinops.org/en/newsletters/2023/11/08/#core-lightning-6783)

**2022**

* [LDK #1425 添加对大容量通道的支持](https://bitcoinops.org/en/newsletters/2022/05/04/#ldk-1425)

**2021**

* [BOLTs #877 移除协议级别的每笔支付金额限制](https://bitcoinops.org/en/newsletters/2021/06/30/#bolts-877)

**2020**

* [2020 年回顾：大容量通道](https://bitcoinops.org/en/newsletters/2020/12/23/#large-channels)
* [LND #4567 添加了一个新的 `-maxchansize` 参数，用于大容量通道](https://bitcoinops.org/en/newsletters/2020/09/23/#lnd-4567)
* [LND 0.11.0-beta 发布，支持默认大容量通道](https://bitcoinops.org/en/newsletters/2020/08/26/#lnd-0-11-0-beta)
* [LND #4429 默认启用对大容量通道的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#lnd-4429)
* [C-Lightning 解决了与 Eclair 开启大容量通道的不兼容问题](https://bitcoinops.org/en/newsletters/2020/05/13/#c-lightning-0-8-2-1)
* [LND 0.10.0-beta 发布，具有创建超过 0.043 BTC 的发票的能力](https://bitcoinops.org/en/newsletters/2020/05/06/#lnd-0-10-0-beta)
* [C-Lightning 0.8.2 发布，支持大容量通道](https://bitcoinops.org/en/newsletters/2020/05/06/#c-lightning-0-8-2)
* [LND #4075 允许创建超过 0.043 BTC 的发票](https://bitcoinops.org/en/newsletters/2020/04/15/#lnd-4075)
* [C-Lightning #3612 添加对 `option_support_large_channel` 的支持](https://bitcoinops.org/en/newsletters/2020/04/08/#c-lightning-3612)
* [Eclair #1323 宣传支持超过约 0.17 BTC 的通道开启](https://bitcoinops.org/en/newsletters/2020/03/11/#eclair-1323)
* [BOLTs #596 更新 BOLT2 以允许超过约 0.17 BTC 的通道开启](https://bitcoinops.org/en/newsletters/2020/02/26/#bolts-596)

**2018**

* [LN 1.1 规范会议：wumbo 通道和支付提案](https://bitcoinops.org/en/newsletters/2018/11/20/#wumbo)

## 参见

* [“wumbo”术语的起源 ( 视频)](https://www.youtube.com/watch?v=--hsVknT1c0)
