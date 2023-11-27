# Addr v2

**addr v2** 是比特币点对点网络协议中 `addr` 消息的新版本提案，用于广播接受进入连接的节点地址。

原始的 `addr` 消息支持转发 128 位 IPv6 地址，并向后兼容 IPv4 以及 [onioncat 编码](https://web.archive.org/web/20121122003543/http://www.cypherpunk.at/onioncat/wiki/OnionCat) 的第二版（v2）Tor 隐藏服务（.onion）地址。然而，v3 版 Tor 隐藏服务地址为 256 位，同样适用于几种其他增强隐私的网络协议的地址。由于这些新型地址类型无法与现有的 `addr` 消息兼容，因此提出了这个新版本的消息。此外，这次更新可能还将允许对消息的其他方面或处理该消息的节点和客户端的行为进行调整。

## 主要代码与文档

* [BIP155](https://github.com/bitcoin/bips/blob/master/bip-0155.mediawiki)

## Optech 新闻稿和网站提及

**2022 年**

* [BTCD v0.23.2 添加了对 addr v2 的支持](https://bitcoinops.org/en/newsletters/2022/10/19/#btcd-v0-23-2-released)

**2021 年**

* [BIPs #1134 阐明了 BIP155 中 `sendaddr2` P2P 特性协商消息的使用](https://bitcoinops.org/en/newsletters/2021/07/07/#bips-1134)
* [Bitcoin Core #20685 添加了对 I2P 的支持，包括 addrv2 消息传播](https://bitcoinops.org/en/newsletters/2021/03/10/#bitcoin-core-20685)
* [Rust Bitcoin 0.26.0 发布，支持第二版 `addr` 消息](https://bitcoinops.org/en/newsletters/2021/01/20/#rust-bitcoin-0-26-0)
* [Bitcoin Core 0.21.0 发布，支持第二版 `addr` 消息](https://bitcoinops.org/en/newsletters/2021/01/20/#bitcoin-core-0-21-0)

**2020 年**

* [2020 年度回顾：第二版 `addr` 消息](https://bitcoinops.org/en/newsletters/2020/12/23/#addrv2)
* [Bitcoin Core #20564 只向协议版本为 70016 的节点发送 addrv2](https://bitcoinops.org/en/newsletters/2020/12/16/#protocol-version)
* [BIP155 更新要求在 `verack` 之前发送 `sendaddrv2` 消息](https://bitcoinops.org/en/newsletters/2020/12/16/#bips-1043)
* [Bitcoin Core #19954 实现了 BIP155 和 Tor v3 支持](https://bitcoinops.org/en/newsletters/2020/10/14/#bitcoin-core-19954)
* [BIPs #907 更新 BIP155 消息，允许最大 512 字节的地址](https://bitcoinops.org/en/newsletters/2020/09/30/#bips-907)
* [Bitcoin Core PR Review Club 讨论关于 `addr` v2 PR 的摘要](https://bitcoinops.org/en/newsletters/2020/08/12/#bitcoin-core-pr-review-club)

**2019 年**

* [关于 addr v2 消息的每个节点地址传播的提议](https://bitcoinops.org/en/newsletters/2019/11/06/#signaling-support-for-address-relay)
* [第二版 `addr` 消息被指定为 BIP155](https://bitcoinops.org/en/newsletters/2019/07/31/#bips-766)
* [提出第二版 `addr` 消息](https://bitcoinops.org/en/newsletters/2019/03/12/#version-2-addr-message-proposed)

## 参见

* [点对点协议 `addr` 消息](https://btcinformation.org/en/developer-reference#addr)
* [匿名网络](https://bitcoinops.org/en/topics/anonymity-networks/)
