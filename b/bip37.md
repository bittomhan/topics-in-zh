---
description: 还涵盖交易布隆过滤（Transaction bloom filtering）和布隆过滤器（Bloom filters）
---

# BIP37

**交易布隆过滤**是一种方法，允许轻量级客户端仅接收影响其钱包的交易数据，从全节点中接收到的交易数量仅限于与其钱包有关的交易（加上可配置数量的额外交易，以产生对客户端所属交易的合理否认）。

[布隆过滤器](https://en.wikipedia.org/wiki/Bloom\_filter)提供了创建一个紧凑过滤器的能力，该过滤器保证匹配指定字符串，并且对其他字符串的误报率可配置。轻量级客户端可以为其所有钱包地址创建一个布隆过滤器，通过 BIP37 中定义的 P2P 协议消息将该过滤器发送到节点，然后从节点请求特殊形式的区块（默克尔区块）。

默克尔区块，也在 BIP37 中定义，将仅包含与先前发送的过滤器匹配的交易，加上区块头和将每个匹配交易连接到区块头中的默克尔根的部分默克尔分支。

如果交易与过滤器匹配，客户端还将接收节点正在中继的新未确认交易的通告。

当 BIP37 受欢迎时，大多数使用它的轻量级客户端在移动设备上运行，具有有限的带宽，因此选择了低误报率以最小化它们的带宽使用。这意味着他们基本上向他们联系的任何节点提供了他们的地址列表。预计注重隐私的用户可以通过设置更高的误报率来减轻这种隐私损失，但研究表明，为了提供合理的否认，这个率需要相当高。

作为附加问题，为 BIP37 过滤器服务的节点必须为每个客户端单独进行过滤，且可能以一种要求节点对每个区块执行大量 CPU 处理的方式创建过滤器。这导致了一系列已知的针对节点的拒绝服务攻击向量。

尽管在实践中 BIP37 允许客户端使用相当少的带宽，但它比基于大型交易数据库的其他远程交易扫描方法更慢且使用更多带宽。今天许多受欢迎的轻量级客户端查询这些数据库，而不是使用交易布隆过滤器。

_注意：本主题仅指 BIP37 交易布隆过滤器。在比特币中还有通用布隆过滤器的使用（例如在比特币核心的交易中继跟踪中），它们不被归入本主题索引。_

## 主要代码和文档

* [BIP37](https://github.com/bitcoin/bips/blob/master/bip-0037.mediawiki)

## Optech 新闻简报及网站提及

**2023**

* [提议从比特币核心中移除 `mempool` 消息支持，可能连同布隆过滤器一起](https://bitcoinops.org/en/newsletters/2023/04/26/#proposed-removal-of-bip35-mempool-p2p-message)

**2021**

* [Rust Bitcoin #580 添加对 BIP37 P2P 网络消息的支持](https://bitcoinops.org/en/newsletters/2021/09/22/#rust-bitcoin-580)
* [BIP37 布隆过滤器连同 `mempool` P2P 消息被弃用的历史](https://bitcoinops.org/en/newsletters/2021/08/25/#is-the-mempool-p2p-message-reliable)

**2020**

* [比特币核心 #19260 断开了不适当发送 filterclear 的节点](https://bitcoinops.org/en/newsletters/2020/06/24/#bitcoin-core-19260)

**2019**

* [比特币核心 0.19 发布，禁用了布隆过滤器](https://bitcoinops.org/en/newsletters/2019/11/27/#deprecated-or-removed-features)
* [比特币核心 PR#16248 添加了布隆过滤器白名单选项](https://bitcoinops.org/en/newsletters/2019/08/21/#bitcoin-core-16248)
* [BRD 字段报告：使用布隆过滤器与原生隔离见证地址](https://bitcoinops.org/en/bech32-sending-support/#brd-field-report)
* [邮件列表关于在比特币核心中禁用布隆过滤器的讨论](https://bitcoinops.org/en/newsletters/2019/07/31/#bloom-filter-discussion)
* [比特币核心 PR#16152 默认禁用布隆过滤器支持](https://bitcoinops.org/en/newsletters/2019/07/24/#bitcoin-core-16152)

## 参见

* [BitcoinJ 中的隐私 \[ 布隆过滤器\]](https://jonasnick.github.io/blog/2015/02/12/privacy-in-bitcoinj/)
* [紧凑区块过滤器](https://bitcoinops.org/en/topics/compact-block-filters/)
