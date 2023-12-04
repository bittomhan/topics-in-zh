# 零确认通道 - Zero-conf channels

**零确认通道**，也称为涡轮通道（turbo channels），是新的单方资助的通道，其中资助者将部分或全部初始资金给予接收方。在通道开放交易获得足够数量的确认之前，这些资金并不安全，因此对于接收方通过标准 LN 协议将部分资金再支付给资助者并没有风险。

例如，Alice 在 Bob 的托管交易所有几个比特币。Alice 请求 Bob 开设一个新通道，向她支付 1.0 比特币。因为 Bob 相信自己不会对刚刚开设的通道进行双重支付，所以他可以允许 Alice 即使在通道开放交易还未获得单次确认的情况下，也可以通过他的节点向第三方 Carol 发送 0.1 比特币。

![](https://bitcoinops.org/img/posts/2021-07-zeroconf-channels.png)

在 2022 年将零确认通道的标准化机制添加到 LN 协议之前，零确认通道已通过各种临时机制使用。

## 主要代码和文档

* [BOLTs #910 规定零确认通道](https://github.com/lightning/bolts/pull/910)

## Optech 新闻简报和网站提及

**2023**

* [双重资助时零确认通道的挑战](https://bitcoinops.org/en/newsletters/2023/05/17/#challenges-with-zero-conf-channels-when-dual-funding)

**2022**

* [2022 年终总结：零确认通道](https://bitcoinops.org/en/newsletters/2022/12/21/#zero-conf-channels)
* [LND 0.15.1-beta 添加对零确认通道的支持](https://bitcoinops.org/en/newsletters/2022/08/31/#lnd-0-15-1-beta)
* [Core Lightning 0.12 添加对零确认通道的支持](https://bitcoinops.org/en/newsletters/2022/08/24/#core-lightning-0-12-0)
* [LND #6816 添加关于如何使用零确认通道的文档](https://bitcoinops.org/en/newsletters/2022/08/17/#lnd-6816)
* [LDK #1401 添加对零确认通道开放的支持](https://bitcoinops.org/en/newsletters/2022/06/08/#ldk-1401)
* [BOLTs #910 添加了一个 `option_zeroconf` 功能位](https://bitcoinops.org/en/newsletters/2022/06/08/#bolts-910)
* [LDK #1311 添加对 SCID 别名字段的支持，有助于零确认通道](https://bitcoinops.org/en/newsletters/2022/03/23/#ldk-1311)

**2021**

* [2021 年终总结：零确认通道开放](https://bitcoinops.org/en/newsletters/2021/12/22/#zeroconfchan)
* [Rust-Lightning #1078 添加了对零确认通道有用的 channel\_type 协商](https://bitcoinops.org/en/newsletters/2021/11/10/#rust-lightning-1078)
* [关于标准化零确认通道开放的讨论](https://bitcoinops.org/en/newsletters/2021/07/07/#zero-conf-channel-opens)

## 参见

* [即时通道（JIT channels）](https://bitcoinops.org/en/topics/jit-channels/)
