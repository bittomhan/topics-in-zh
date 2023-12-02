# 反签名 - Countersign

**反签名**是一种协议的构想，它将允许拥有彼此公钥的客户端和服务器协商认证，而无需任一参与者向第三方泄露任何身份信息。

这将使得在互联网上为矿工或交易所安全地设置白名单节点变得更加容易，或允许轻量级钱包确保它们连接到可信节点。通过在不向第三方泄露身份的情况下实现认证，那些在匿名网络（如 Tor）上的节点或简单地更改了 IP 地址的节点就不会被追踪到网络身份。

该协议应与 [第 2 版 P2P 传输协议（version 2 P2P transport protocol）](https://bitcoinops.org/en/topics/v2-p2p-transport/) 兼容。

## 主要代码和文档

* [Countersign](https://gist.github.com/sipa/d7dcaae0419f10e5be0270fada84c20b)

## Optech 新闻通讯和网站提及

**2022**

* [CoreDev.tech 记录：第 2 版 P2P 加密传输和反签名](https://bitcoinops.org/en/newsletters/2022/10/26/#transport-encryption)

**2019**

* [CoreDev.tech 会议：第 2 版 P2P 传输和反签名](https://bitcoinops.org/en/newsletters/2019/06/12/#v2-p2p)

**2018**

* [2018 年度回顾：不可追踪的认证](https://bitcoinops.org/en/newsletters/2018/12/28/#countersign)

## 参见

* [第 2 版 P2P 传输（Version 2 P2P Transport）](https://bitcoinops.org/en/topics/v2-p2p-transport/)
