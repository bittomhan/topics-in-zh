# 对等节点存储 - Peer storage

**对等节点存储**是一种可选服务，其中节点接受来自其对等节点（尤其是通道对方）的少量频繁更新的加密数据。它根据请求（如重新建立连接）向对等节点提供该数据的最新版本。该数据可以是对等节点最新通道状态的备份，即使他们丢失了本地状态，也能够继续使用该通道。

_此主题描述是一个存根。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/peer-storage.md) _提供有关该主题的更多背景信息。_

## 主要代码和文档

* [BOLTs #881: 对等节点备份存储](https://github.com/lightning/bolts/pull/881)

## Optech 新闻简报和网站提及

**2023**

* [与对等节点存储备份相比的过时状态欺诈证明](https://bitcoinops.org/en/newsletters/2023/08/23/#fraud-proofs-for-outdated-backup-state)
* [Core Lightning #5361 为对等节点存储备份添加了实验性支持](https://bitcoinops.org/en/newsletters/2023/02/15/#core-lightning-5361)

**2021**

* [仅使用 BIP32 种子恢复闪电网络通道](https://bitcoinops.org/en/newsletters/2021/05/05/#closing-lost-channels-with-only-a-bip32-seed)
