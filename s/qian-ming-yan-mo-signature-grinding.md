---
description: 也涵盖低 -r 研磨 (Low-r grinding)
---

# 签名研磨  - Signature grinding

**低 -r 研磨 (Low-r grinding)**是一种钱包优化技术，钱包会为同一交易不断生成新的 ECDSA 签名，直到找到一个其 _r_ 值在范围的下半部分的签名，从而使其能够用比位于范围上半部分的签名少一个字节的方式进行编码。

这种优化只适用于使用 ECDSA 的传统交易和 segwit v0 交易。在 [taproot](https://bitcoinops.org/en/topics/taproot/) 交易中的签名无法进一步缩短。

大约一半的 ECDSA 交易预计会有高 -r 值，另一半预计会有低 -r 值，因此在传统交易中，研磨平均每个签名节省 0.5 vbytes，在 segwit v0 交易中节省 0.125 vbytes。

## Optech 新闻简报和网站提及

**2022**

* [BDK #779 添加了创建低 -r 签名的支持](https://bitcoinops.org/en/newsletters/2022/11/02/#bdk-779)
* [LDK #1388 默认添加了创建低 -r 签名的支持](https://bitcoinops.org/en/newsletters/2022/04/06/#ldk-1388)

**2019**

* [C-Lightning #3220 开始始终创建低 r 值的签名](https://bitcoinops.org/en/newsletters/2019/11/06/#c-lightning-3220)

**2018**

* [Bitcoin Core 钱包开始只创建低 -r 签名](https://bitcoinops.org/en/newsletters/2018/08/14/#bitcoin-core-wallet-to-begin-only-creating-low-r-signatures)

## 参见

* [什么是签名研磨？](https://bitcoin.stackexchange.com/questions/111660/what-is-signature-grinding)
