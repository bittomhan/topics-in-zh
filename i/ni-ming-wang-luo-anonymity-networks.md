---
description: 也涵盖 Tor 和匿名网络（Anonymity Networks）
---

# I2P

**匿名网络** 是一种系统，它允许网络通信而无需发送者或接收者向对方公开他们的 IP 地址。其中最知名的是 Tor 和 I2P。

使用匿名网络可以大大提高比特币软件的隐私性。特别是在发送自己的交易时更为有益。对于不为其他节点转发交易的轻量级客户端而言，这一点尤其重要，因为他们的 IP 地址发送的任何交易都很容易与他们的网络身份关联起来。

但在某些情况下，使用匿名网络也可能是一种负担；例如：

* **追踪最佳区块链（Following the best block chain）** 对匿名网络上的全节点和轻量级客户端来说是一个主要挑战。由于匿名网络允许创建大量假身份，仅使用这些网络的系统容易受到可能导致 [日蚀攻击（Eclipse Attacks）](https://bitcoinops.org/en/topics/eclipse-attacks/) 的女巫攻击，这种攻击向客户端和节点提供与网络其他部分不同的区块链，可能导致资金损失。
* **延迟（Latency）** 对于设计为快速的路由合约协议系统（例如 LN）可能是一个问题。然而，对于许多终端用户来说，为了显著提高隐私，稍微慢一点的速度是可以接受的。

与比特币分开的匿名网络，如 Tor 和 I2P，也可以与比特币中改善隐私的技术（如 [蒲公英（Dandelion）](https://bitcoinops.org/en/topics/dandelion/)）结合使用。

注意：Tor 洋葱服务（Tor Onion Services）不应与 LN 中使用的洋葱加密（Onion Encryption）混淆。尽管两者都源自同样的保护隐私的想法，但它们是两个不同的系统。

## Optech 新闻简报和网站提及

**2023**

* [Bitcoin Core #27411 停止在其他网络上宣布本地节点的 Tor 或 I2P 地址](https://bitcoinops.org/en/newsletters/2023/07/19/#bitcoin-core-27411)

**2022**

* [Bitcoin Core #25355 添加了对瞬态 I2P 地址的支持](https://bitcoinops.org/en/newsletters/2022/09/07/#bitcoin-core-25355)

**2021**

* [Bitcoin Core #23077 通过 CJDNS 启用地址转发](https://bitcoinops.org/en/newsletters/2021/11/17/#bitcoin-core-23077)
* [Bitcoin Core 22.0 添加了对 I2P 连接的支持并移除了 v2 Tor 连接](https://bitcoinops.org/en/newsletters/2021/09/15/#bitcoin-core-22-0)
* [Bitcoin Core #22112 将 I2P 地址的默认端口更改为 0 而不是 8333](https://bitcoinops.org/en/newsletters/2021/07/21/#bitcoin-core-22112)
* [Bitcoin Core #22050 放弃对已弃用的 v2 Tor 洋葱服务的支持](https://bitcoinops.org/en/newsletters/2021/06/09/#bitcoin-core-22050)
* [Bitcoin Core #21594 在 `getnodeaddresses` RPC 中添加了网络类型字段](https://bitcoinops.org/en/newsletters/2021/04/14/#bitcoin-core-21594)
* [Bitcoin Core #20197 更新了逐出逻辑以保留长时间运行的洋葱节点](https://bitcoinops.org/en/newsletters/2021/04/07/#bitcoin-core-20197)
* [问题：如何将 I2P 与 Bitcoin Core 一起使用？](https://bitcoinops.org/en/newsletters/2021/03/31/#how-can-i-use-bitcoin-core-with-the-anonymous-network-protocol-i2p)
* [Bitcoin Core #20685 添加了对 I2P 隐私网络的支持](https://bitcoinops.org/en/newsletters/2021/03/10/#bitcoin-core-20685)
* [Bitcoin Core 0.21.0 发布，支持 Tor v3 洋葱地址](https://bitcoinops.org/en/newsletters/2021/01/20/#bitcoin-core-0-21-0)
* [Bitcoin Core GUI #162 在 GUI 节点窗口中添加了网络类型信息](https://bitcoinops.org/en/newsletters/2021/01/06/#bitcoin-core-gui-162)

**2020**

* [年度回顾：对 Tor v3 洋葱地址的支持](https://bitcoinops.org/en/newsletters/2020/12/23/#addrv2)
* [Bitcoin Core #19954 完成了 BIP155 addr v2 的实现](https://bitcoinops.org/en/newsletters/2020/10/14/#bitcoin-core-19954)
* [Bitcoin Core #19991 启用了追踪来自洋葱节点的入站连接](https://bitcoinops.org/en/newsletters/2020/10/07/#bitcoin-core-19991)
* [Bitcoin Core PR 审查俱乐部关于 BIP155 addr v2 提议实现的讨论](https://bitcoinops.org/en/newsletters/2020/08/12/#bitcoin-core-pr-review-club)
* [Blockstream Green 桌面版发布，支持 Tor](https://bitcoinops.org/en/newsletters/2020/06/17/#desktop-version-of-blockstream-green-wallet)
* [关于 LND 0.10 的改进演讲，包括更好的 Tor 支持](https://bitcoinops.org/en/newsletters/2020/05/06/#lnd-v0-10)
* [BOLTs #751 更新 BOLT7，以更好地处理多网络节点公告](https://bitcoinops.org/en/newsletters/2020/03/25/#bolts-751)
* [CKBunker 允许为启用 Tor 的 Coldcard 指定支付条件](https://bitcoinops.org/en/newsletters/2020/02/19/#ckbunker-using-psbts-for-an-hsm)
* [Eclair #1278 允许用户在使用洋葱服务时跳过使用 SSL](https://bitcoinops.org/en/newsletters/2020/02/05/#eclair-1278)

**2019**

* [C-Lightning #3155 添加了使用静态洋葱服务地址的选项](https://bitcoinops.org/en/newsletters/2019/12/11/#c-lightning-3155)
* [Blockstream Green 内置 Tor 支持，适用于 iOS 和 Android](https://bitcoinops.org/en/newsletters/2019/10/23/#blockstream-green-tor-support)
* [BIPs #766 将 BIP155 分配给 v3 洋葱地址的 addr v2 提案](https://bitcoinops.org/en/newsletters/2019/07/31/#bips-766)
* [Bitcoin Core #15651 在监听 Tor 时始终绑定到默认端口](https://bitcoinops.org/en/newsletters/2019/06/26/#bitcoin-core-15651)
* [BIP 提出新的地址转发消息以支持 Tor v3 洋葱地址](https://bitcoinops.org/en/newsletters/2019/03/12/#version-2-addr-message-proposed)
* [Eclair #736 添加了使用和成为洋葱服务的支持](https://bitcoinops.org/en/newsletters/2019/02/12/#eclair-736)

**2018**

* [LND #1516 添加了自动设置 v3 洋葱服务的支持](https://bitcoinops.org/en/newsletters/2018/09/18/#lnd-1516)

## 参见

* [蒲公英（Dandelion）](https://bitcoinops.org/en/topics/dandelion/)
* [Addr v2](https://bitcoinops.org/en/topics/addr-v2/)
