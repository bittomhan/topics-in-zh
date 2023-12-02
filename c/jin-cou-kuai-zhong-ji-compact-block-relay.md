---
description: 同时涵盖 BIP152
---

# 紧凑块中继 - Compact Block Relay

**紧凑块中继**是一种协议，它允许具有大致相似的未确认交易集的两个节点在传输一个确认这些相同交易的区块时，最小化所需的带宽和延迟。

默认情况下，大多数全节点都配置为接收中继的未确认交易，这些节点将这些交易存储在它们的内存池（mempool）中，并进一步中继给其他节点。最终这些交易到达矿工，矿工试图将它们纳入一个区块。当这个新区块本身被中继回节点时，它通常几乎完全由节点的内存池中已有的交易组成。

第二次中继这些交易是多余的，正是这种冗余性，[BIP152](https://github.com/bitcoin/bips/blob/master/bip-0152.mediawiki) 紧凑块旨在消除。发送节点通过用每个对等节点的快速 6 字节非加密哈希代替其认为其对等节点已拥有的每个交易，来构造一个紧凑块。这可以将包含数千个交易的多兆字节区块压缩到仅几千字节。这直接减少了带宽。间接地，它还显著减少了延迟，因为 TCP 比大量数据更快地传播较小量的数据。

对于生成节点认为其对等节点不知道的任何交易，它发送完整的交易。

接收对等节点对其内存池中所有交易的见证交易标识符（wtxid）进行哈希处理。然后，它将紧凑块中的每个 wtxid 哈希替换为其内存池中的完整交易。如果紧凑块中的任何 wtxid 哈希与接收对等节点的内存池中的交易不匹配，它会从发送节点请求该交易。

为了最大化带宽和延迟改进，紧凑块可以以两种不同模式使用：

* [低带宽模式](https://bitcoinops.org/en/topics/compact-block-relay/#low-bandwidth-mode)旨在与大多数对等节点一起使用。当一个节点了解到一个新区块时，它会向其 BIP152 低带宽对等节点宣布该区块的头部哈希。只有当一个对等节点请求紧凑块时，才会发送额外的数据。这避免了向可能已经从其他对等节点接收到该区块的对等节点发送数据。
* [高带宽模式](https://bitcoinops.org/en/topics/compact-block-relay/#high-bandwidth-mode)旨在仅与特别请求该模式的少数对等节点一起使用。当一个节点接收到一个区块时，它验证其头部包含适量的工作量证明（PoW），然后，不进行任何其他重要验证，立即将其作为紧凑块发送给其高带宽模式对等节点。这允许区块快速在网络上传播，但代价是节点有时会向已经从另一个节点接收到该区块的对等节点发送紧凑块。由于紧凑块比原始区块小得多，这种“高带宽”模式通常仍然使用的带宽比 BIP152 之前的区块中继更少。

BIP152 还指定了两个版本的紧凑块：

* 版本 1 使用 txid 的哈希。
* 版本 2 使用 wtxid 的哈希。

保留紧凑块中继的优势通常被引用为一种尝试在节点之间保持内存池和中继策略一致性的原因——节点的内存池差异越大，紧凑块在最小化带宽和延迟方面的效果就越小。

## 主要代码和文档

* [BIP152](https://github.com/bitcoin/bips/blob/master/bip-0152.mediawiki)

## Optech 新闻简报和网站提及

**2023**

* [Bitcoin Core #27626 允许从多个对等节点并行下载紧凑块](https://bitcoinops.org/en/newsletters/2023/05/31/#bitcoin-core-27626)

**2022**

* [关于不一致的内存池及其对紧凑块中继可能影响的讨论](https://bitcoinops.org/en/newsletters/2022/11/02/#better-peering-involves-tradeoffs)
* [Rust Bitcoin #1088 添加了紧凑块的结构和方法](https://bitcoinops.org/en/newsletters/2022/08/03/#rust-bitcoin-1088)
* [Bitcoin Core #20799 禁用了 v1 紧凑块中继；v2 仍然启用](https://bitcoinops.org/en/newsletters/2022/05/25/#bitcoin-core-20799)

**2021**

* [为 `blocksonly` 节点禁用紧凑块中继](https://bitcoinops.org/en/newsletters/2021/09/08/#bitcoin-core-pr-review-club)
* [Bitcoin Core PR Review Club 关于停止支持 v1 紧凑块的讨论](https://bitcoinops.org/en/newsletters/2021/02/10/#bitcoin-core-pr-review-club)
* [Bitcoin Core #20764 向 bitcoin-cli 添加了 BIP152 高带宽指示器](https://bitcoinops.org/en/newsletters/2021/02/10/#bitcoin-core-20764)

**2020**

* [Bitcoin Core #19776 使用 BIP152 对等节点状态更新了 `getpeerinfo` RPC](https://bitcoinops.org/en/newsletters/2020/12/16/#bitcoin-core-19776)
* [不对紧凑块效率后向支持分叉塔普罗特的后果](https://bitcoinops.org/en/newsletters/2020/07/29/#dont-relay-taproot)
