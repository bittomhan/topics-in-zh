# 日蚀攻击 - Eclipse attacks

**日蚀攻击**发生在一个节点被隔离，无法连接到任何诚实的节点，但仍然连接到至少一个恶意节点。

在没有与诚实节点的连接的情况下，被日蚀的节点不会接收到最新的、拥有最多工作量证明的区块链上的区块。这使得攻击者有无限的时间来生成包含双重支付的区块，因此即使是拥有少量哈希率的攻击者也能欺骗受害者接受已确认的双重支付。

攻击者还将控制受害者节点接收的交易。这允许他们告诉节点一些网络上通常不可用的交易，以促使受害者的节点采取行动（例如，攻击者仅向被日蚀的节点发送关闭闪电网络（LN）通道的交易）。

最后，攻击者可以控制受害者可以发送的交易。这使攻击者能够阻止受害者发送时间敏感的交易，如 LN 罚金交易。这也意味着受害者生成的任何交易都可以被明确地识别为来自受害者——这是隐私的损失。

为了防止日蚀攻击，节点运营商被鼓励在[多个网络接口](https://en.wikipedia.org/wiki/Multihoming)上运行他们的节点，并在可能的情况下，至少通过安全网络（例如 VPN）保持与其他几个节点的连接。在只有单一接口的节点的可能限制范围内，比特币核心（Bitcoin Core）开发者努力确保节点连接到一个大而多样化的节点集，以减少节点的每一个对等方都是同一个[Sybil 攻击者](https://en.wikipedia.org/wiki/Sybil\_attack)的机会。

## 主要代码和文档

* [比特币点对点网络上的日蚀攻击](https://eprint.iacr.org/2015/263.pdf)

## Optech 新闻简报和网站提及

**2023**

* [Bitcoin Core #27213 将尝试在每个可达网络上开启并维持一个连接](https://bitcoinops.org/en/newsletters/2023/08/16/#bitcoin-core-27213)

**2021**

* [LND 0.14.0-beta 包括通过共享区块头增加的额外日蚀攻击保护](https://bitcoinops.org/en/newsletters/2021/11/24/#lnd-0-14-0-beta)
* [提议的 `disabletx` 消息有助于允许更多的仅区块传输的对等方](https://bitcoinops.org/en/newsletters/2021/01/13/#proposed-disabletx-message)

**2020**

* [2020 年回顾：针对闪电网络节点的快速日蚀攻击](https://bitcoinops.org/en/newsletters/2020/12/23/#fast-ln-eclipse-attacks)
* [Bitcoin Core PR #19858 改进了对日蚀攻击的隔离阻力](https://bitcoinops.org/en/newsletters/2020/12/16/#bitcoin-core-19858)
* [关于 PR #19858 的评论会议，使日蚀攻击更加困难](https://bitcoinops.org/en/newsletters/2020/12/09/#bitcoin-core-pr-review-club)
* [Eclair #1545 添加了多个头部来源以使日蚀攻击更加困难](https://bitcoinops.org/en/newsletters/2020/11/11/#eclair-1545)
* [CVE-2018-17145 InvDoS 攻击本可用于日蚀节点](https://bitcoinops.org/en/newsletters/2020/09/16/#inventory-out-of-memory-denial-of-service-attack-invdos)
* [Bitcoin Core #19670 为仅区块传输的对等方保留了入站槽位](https://bitcoinops.org/en/newsletters/2020/09/09/#bitcoin-core-19670)
* [时间扩张攻击：使用日蚀攻击窃取闪电网络节点的资金](https://bitcoinops.org/en/newsletters/2020/06/10/#time-dilation-attacks-against-ln)
* [Bitcoin Core 0.20 发布，包含提高日蚀防御的 asmap 特性](https://bitcoinops.org/en/newsletters/2020/06/10/#bitcoin-core-0-20-0)
* [关于攻击比特币核心的演讲，包括使用日蚀攻击](https://bitcoinops.org/en/newsletters/2020/05/06/#attacking-bitcoin-core)
* [Bitcoin Core #17428 锚定连接的评论会议讨论](https://bitcoinops.org/en/newsletters/2020/03/11/#bitcoin-core-pr-review-club)
* [Bitcoin Core #16702 基于 ASN 而不是 IP 地址前缀选择对等方](https://bitcoinops.org/en/newsletters/2020/02/05/#bitcoin-core-16702)

**2019**

* [2019 年回顾：erlay 和其他 P2P 改进](https://bitcoinops.org/en/newsletters/2019/12/28/#erlay-and-other-p2p-improvements)
* [关于闪电网络节点上的日蚀攻击的讨论](https://bitcoinops.org/en/newsletters/2019/12/18/#discussion-of-eclipse-attacks-on-ln-nodes)
* [使用仅区块传输连接预防日蚀攻击](https://bitcoinops.org/en/newsletters/2019/09/11/#bitcoin-core-15759)
* [基于 ASN 而不是地址前缀区分对等方](https://bitcoinops.org/en/newsletters/2019/06/26/#differentiating-peers-based-on-asn-instead-of-address-prefix)

## 参见

* [匿名网络（Anonymity networks）](https://bitcoinops.org/en/topics/anonymity-networks/)
