# 交易起源隐私 - Transaction origin privacy

**交易起源隐私**是指隐藏交易起源于网络监控的能力。

如果窃听者可以看到每个节点转发的每笔交易，他们可以假设首个发送交易的节点就是该交易的起源节点。这意味着该节点 IP 地址下的某人创建了该交易。无论这种推测是否正确，这种能力都对用户隐私有害。

即使无法对整个比特币网络进行监视，也有许多方法试图定位哪个节点发起了交易。开发者已经在提高交易起源隐私方面付出了巨大努力。一些先前和正在进行的努力包括：

* **闪电网络：**尽管链上 LN 交易仍需要交易起源隐私，但通过洋葱加密消息路由的链下 LN 支付对抗针对链上比特币交易的许多技术更具抵抗力。
* [匿名网络](https://bitcoinops.org/en/topics/anonymity-networks)：比特币核心已经添加了通过 Tor、I2P 和 CJDNS 加密中继交易和其他数据的支持。其他一些比特币程序支持部分或所有这些协议。加密使窃听者更难以可靠地确定交易的起源。
* [v2 P2P 传输](https://bitcoinops.org/en/topics/v2-p2p-transport)：此协议将为比特币程序提供交易和其他数据的本地加密。
* [蒲公英](https://bitcoinops.org/en/topics/dandelion/)：此协议将允许未发起交易的节点首先公开广播交易，可能使确定实际起源变得更加困难。如果与加密（无论是原生还是通过匿名网络）结合使用，蒲公英将更加有效。
* **内存池重广播：**比特币协议无法向钱包保证其未确认交易已被诚实节点和矿工接收。这意味着钱包可能需要定期重播未确认交易。每次重播都增加了监视者确定哪个 IP 地址发起交易的机会。比特币核心开发者一直在努力让所有节点定期从它们的内存池中重播一些未确认交易，这样就不清楚重播是由交易中的钱包还是某个随机节点发起的。重播也可能除了隐私以外还有其他有益的效果。

## 主要代码和文档

* [比特币 Wiki：隐私—流量分析](https://en.bitcoin.it/wiki/Privacy#Traffic\_analysis)

## Optech 新闻简报和网站提及

**2023**

* [频繁的交易重广播的替代循环缓解以及可能降低隐私的风险](https://bitcoinops.org/en/newsletters/2023/10/25/#frequent-rebroadcasting)

**2020**

* [比特币核心 #19109 为跟踪最近交易公告添加了每个节点的滚动布隆过滤器](https://bitcoinops.org/en/newsletters/2020/07/22/#bitcoin-core-19109)
* [比特币核心 #18861 仅允许节点请求已向该节点告知该交易的节点](https://bitcoinops.org/en/newsletters/2020/05/27/#bitcoin-core-18861)

**2019**

* [演讲摘要：‘TxProbe：使用孤立交易发现比特币网络拓扑’](https://bitcoinops.org/en/newsletters/2019/09/18/#txprobe-discovering-bitcoin-s-network-topology-using-orphan-transactions)
* [比特币核心 #15834 修复了在 #14897 中引入的一个半随机顺序请求交易的 bug](https://bitcoinops.org/en/newsletters/2019/06/19/#bitcoin-core-15834)
* [比特币核心 #14897 引入了请求交易的半随机顺序](https://bitcoinops.org/en/newsletters/2019/02/12/#bitcoin-core-14897)

## 参见

* [匿名网络](https://bitcoinops.org/en/topics/anonymity-networks/)
* [V2 P2P 传输](https://bitcoinops.org/en/topics/v2-p2p-transport/)
* [蒲公英](https://bitcoinops.org/en/topics/dandelion/)
