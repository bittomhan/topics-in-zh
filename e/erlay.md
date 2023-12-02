# Erlay

**Erlay** 是一个提议，旨在提高比特币全节点之间转发未确认交易的带宽效率。

在目前使用的比特币流言协议中，大多数全节点被配置为将每个新交易广告给所有对等节点，除非他们之前已经从该对等节点接收到有关该交易的广告。考虑到每个节点只需要从其一个对等节点处了解交易，每个广告的交易 ID 至少需要 32 字节，且节点默认最多有 125 个对等节点，这消耗了大量冗余带宽。

Erlay 是一个两部分的提议，首先限制了节点直接广告交易的对等节点数量（默认：8），其次，使用基于 [libminisketch](https://github.com/sipa/minisketch) 的集合协调技术与其余对等节点进行交互，以避免发送接收方对等节点已经看到的任何交易的交易 ID。

Erlay 比当前协议更好地适应更大数量的对等节点，使得节点实际接受比现在更多的连接成为可能。这将提高转发网络对偶然和蓄意网络分区的鲁棒性。

## 主要代码和文档

* [BIP330](https://github.com/bitcoin/bips/blob/master/bip-0330.mediawiki)
* [Erlay](https://arxiv.org/pdf/1905.10518.pdf)

## Optech 新闻简报和网站提及

**2022**

* [关于不一致的内存池及其如何影响 Erlay 的讨论](https://bitcoinops.org/en/newsletters/2022/11/02/#better-peering-involves-tradeoffs)
* [比特币核心 #23443 添加了用于 Erlay 的 `sendtxrcncl` 协商消息](https://bitcoinops.org/en/newsletters/2022/10/26/#bitcoin-core-23443)
* [BIPs #1370 更新了 Erlay 的 BIP330 规范](https://bitcoinops.org/en/newsletters/2022/10/05/#bips-1370)
* [PR 评论会：#23443 实现 Erlay 支持信号](https://bitcoinops.org/en/newsletters/2022/01/12/#bitcoin-core-pr-review-club)

**2021**

* [PR 评论会：#18261 实现 Erlay](https://bitcoinops.org/en/newsletters/2021/03/10/#bitcoin-core-pr-review-club)

**2019**

* [2019 年回顾：Erlay](https://bitcoinops.org/en/newsletters/2019/12/28/#erlay-and-other-p2p-improvements)
* [作为 BIP330 发布的与 Erlay 兼容的交易协调协议](https://bitcoinops.org/en/newsletters/2019/11/13/#bips-851)
* [启用 Erlay 兼容性的草案 BIP](https://bitcoinops.org/en/newsletters/2019/10/02/#draft-bip-for-enabling-erlay-compatibility)
* [Erlay 提议](https://bitcoinops.org/en/newsletters/2019/06/05/#erlay-proposed)

## 参见

* [Minisketch](https://bitcoinops.org/en/topics/minisketch/)
