---
description: 同时涵盖显性 ASIC 提速（Overt ASICBoost）和隐性 ASIC 提速（Covert ASICBoost）
---

# ASIC 提速（ASICBoost）

**ASIC 提速（ASICBoost）** 是一种特别构造比特币区块头的技术，旨在减少大约15%寻找特定量工作量证明（proof of work）所需的操作次数。

ASIC 提速可以以两种形式实现：

* **显性 ASIC 提速（Overt ASICBoost）** 需要操纵区块头的 nVersion 字段。这在区块链上是明显可见的。建议希望使用显性 ASIC 提速的矿工使用[BIP320](https://github.com/bitcoin/bips/blob/master/bip-0320.mediawiki)保留的通用版本位。
*   **隐性 ASIC 提速（Covert ASICBoost）** 需要操纵区块头的默克尔根（merkle root）字段的一部分。这可以不被检测到地完成，尽管天真的实现通常会留下线索。

    隐性 ASIC 提速与包含对其交易的次要承诺的区块不兼容，如包含隔离见证（segwit）交易的任何区块。当发现一家强烈反对隔离见证的矿机硬件制造商秘密设计了其ASIC中的功能以使用隐性ASIC提速时，这产生了[争议](https://bitcoinops.org/en/topics/soft-fork-activation/#2016-7-bip9-bip148-and-bip91-the-bip141143-segwit-activation)。

## 主要代码和文档

* [AsicBoost ——比特币挖矿的速度提升](https://arxiv.org/abs/1604.00575)

## Optech 新闻简报和网站提及

**2021年**

* [关于区块模板与实际区块的问题：ASICBoost 解释了其中一个差异](https://bitcoinops.org/en/newsletters/2021/04/28/#why-does-the-mined-block-differ-so-much-from-the-block-template)

**2019年**

* [比特币核心 #15471 移除由显性 ASIC 提速使用错误触发的警告](https://bitcoinops.org/en/newsletters/2019/03/05/#bitcoin-core-15471)

**2018年**

* [S9矿机支持显性 ASIC 提速](https://bitcoinops.org/en/newsletters/2018/10/30/#overt-asicboost-support-for-s9-miners)

## 参见

* [BIP320：通用目的使用的 nVersion 位](https://github.com/bitcoin/bips/blob/master/bip-0320.mediawiki)
