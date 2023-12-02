---
description: 同时涵盖盲化路径（Blinded Paths）、隐藏目的地（Hidden Destinations）和会合路由（Rendez-vous Routing）
---

# 路径盲化 - Route Blinding

**会合路由**、**隐藏目的地**和**盲化路径**是一些技术的名称，这些技术允许闪电网络（LN）节点向未公布的节点发送付款，而不需要了解该节点在网络拓扑中的位置或它与其他节点共享的通道。

_这个主题描述是一个存根。我们欢迎通过_[_拉取请求（pull request）_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/rendez-vous-routing.md)_提供有关该主题的更多背景信息。_

## 主要代码和文档

* [路径盲化](https://github.com/lightningnetwork/lightning-rfc/blob/route-blinding/proposals/route-blinding.md)

## Optech 新闻简报和网站提及

**2023**

* [LND #7267 使得可以创建到盲化路径的路由](https://bitcoinops.org/en/newsletters/2023/10/18/#lnd-7267)
* [LDK #2413 添加了发送和接收使用盲化路径的付款的支持](https://bitcoinops.org/en/newsletters/2023/09/20/#ldk-2413)
* [LDK #2411 和 #2412 添加了为盲化付款构建支付路径的 API](https://bitcoinops.org/en/newsletters/2023/08/30/#ldk-2411)
* [LND #7710 添加了检索 HTLC 额外数据的能力以支持路径盲化](https://bitcoinops.org/en/newsletters/2023/06/28/#lnd-7710)
* [LDK #2120 添加了找到使用盲化路径的接收者路由的支持](https://bitcoinops.org/en/newsletters/2023/06/28/#ldk-2120)
* [BOLTs #765 将路径盲化添加到 LN 规范](https://bitcoinops.org/en/newsletters/2023/04/05/#bolts-765)
* [Eclair #2482 允许使用盲化路由发送付款](https://bitcoinops.org/en/newsletters/2023/01/04/#eclair-2482)

**2022**

* [Core Lightning #5646 添加了转发盲化付款的支持](https://bitcoinops.org/en/newsletters/2022/11/02/#core-lightning-5646)
* [Eclair #2418 和 #2408 添加了接收使用盲化路由发送的付款的支持](https://bitcoinops.org/en/newsletters/2022/09/21/#eclair-2418)
* [Eclair #2253 添加了中继盲化付款的支持](https://bitcoinops.org/en/newsletters/2022/08/03/#eclair-2253)
* [关于 LNURL 或提议有效盲化路径的需求的讨论](https://bitcoinops.org/en/newsletters/2022/06/15/#blinded-paths)

**2020**

* [C-Lightning #3623 添加了使用盲化路径支付付款的最小实现](https://bitcoinops.org/en/newsletters/2020/04/22/#c-lightning-3623)
* [C-Lightning #3600 添加了使用盲化路径的洋葱消息的实验性支持](https://bitcoinops.org/en/newsletters/2020/04/08/#c-lightning-3600)
* [诱饵节点和轻量级会合路由（盲化路径）](https://bitcoinops.org/en/newsletters/2020/02/19/#decoy-nodes-and-lightweight-rendez-vous-routing)

**2018**

* [闪电网络协议 1.1 目标：隐藏目的地](https://bitcoinops.org/en/newsletters/2018/11/20/#hidden-destinations)

## 参见

* [未公布的通道（Unannounced Channels）](https://bitcoinops.org/en/topics/unannounced-channels/)
* [洋葱消息（Onion Messages）](https://bitcoinops.org/en/topics/onion-messages/)- [提议（Offers）](https://bitcoinops.org/en/topics/offers/)
