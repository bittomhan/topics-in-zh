---
description: 同时涵盖 BIP156
---

# 蒲公英协议 - Dandelion

**蒲公英协议**是一个隐私增强提案，它允许交易首先从一个节点串行传播到另一个节点，然后再从一个节点广播给其所有对等节点。

这种传播行为有助于隐藏发起交易的节点，特别是如果一些参与最初串行中继（“茎阶段”）的节点使用 Tor 或类似于 [v2 P2P 传输](https://bitcoinops.org/en/topics/v2-p2p-transport/)的东西加密其比特币协议流量的话。

## 主要代码和文档

* [BIP156](https://github.com/bitcoin/bips/blob/master/bip-0156.mediawiki)

## Optech 新闻简报和网站提及

**2019**

* [Erlay 与 BIP156 兼容](https://bitcoinops.org/en/newsletters/2019/06/05/#erlay-proposed)
* [需要更多审查或开发的 PR](https://bitcoinops.org/en/newsletters/2019/02/19/#bitcoin-core-freeze-week)
* [比特币核心中 BIP156 蒲公英实施的难点是什么？](https://bitcoinops.org/en/newsletters/2019/01/29/#what-s-the-hold-up-implementing-bip156-dandelion-in-bitcoin-core)

**2018**

* [2018 年度回顾值得注意的发展：BIP156 蒲公英](https://bitcoinops.org/en/newsletters/2018/12/28/#dandelion)
* [研究蒲公英抗拒绝服务攻击的茎路由](https://bitcoinops.org/en/newsletters/2018/08/21/#dandelion-protocol-dos-resistant-stem-routing)
* [蒲公英路由选择的讨论](https://bitcoinops.org/en/newsletters/2018/07/03/#dandelion-transaction-relay)

## 参见

* [交易起源隐私](https://bitcoinops.org/en/topics/transaction-origin-privacy/)
* [匿名网络](https://bitcoinops.org/en/topics/anonymity-networks/)
* [第二版加密 P2P 传输](https://bitcoinops.org/en/topics/v2-p2p-transport/)
