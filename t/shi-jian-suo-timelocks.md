# 时间锁 - Timelocks

**时间锁**是一种限制，它可以防止交易或输出的花费在达到特定的成熟时间或区块高度之前被确认。

_此主题描述是一个草稿。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/timelocks.md) _提供有关该主题的更多背景信息。_

## 主要代码和文档

* [BIP65 `OP_CHECKLOCKTIMEVERIFY` 用于脚本中的绝对时间锁](https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki)
* [BIP68 使用共识强制序列号的相对时间锁](https://github.com/bitcoin/bips/blob/master/bip-0068.mediawiki)
* [BIP112 `OP_CHECKSEQUENCEVERIFY` 用于脚本中的相对时间锁](https://github.com/bitcoin/bips/blob/master/bip-0112.mediawiki)

## Optech 新闻简报和网站提及

**2021**

* [使用 CPFP 费用提升在 LN 中处理时间锁的挑战](https://bitcoinops.org/en/newsletters/2021/04/21/#using-anchor-outputs-by-default-in-lnd)

**2020**

* [BOLTs #803 更新 BOLT5，提供处理接近成熟的时间锁的建议](https://bitcoinops.org/en/newsletters/2020/12/16/#bolts-803)
* [关于时间锁和高度锁之间冲突的研究](https://bitcoinops.org/en/newsletters/2020/09/23/#research-into-conflicts-between-timelocks-and-heightlocks)
* [使用一区块相对时间锁防止 coinswaps 中的固定问题](https://bitcoinops.org/en/newsletters/2020/09/09/#continued-coinswap-discussion)
* [在单链上仅需要时间锁的新型跨链 coinswap 构造](https://bitcoinops.org/en/newsletters/2020/05/20/#two-transaction-cross-chain-atomic-swap-or-same-chain-coinswap)
* [使用递减的锁定时间代替 eltoo 进行状态链实现](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)

**2019**

* [基于长期时间锁的忠诚债券](https://bitcoinops.org/en/newsletters/2019/07/31/#fidelity-bonds-for-improved-sybil-resistance)
* [Lightning Loop 发布，使用带有链上时间锁的 submarine swaps](https://bitcoinops.org/en/newsletters/2019/03/26/#loop-announced)

**2018**

* [交易固定作为涉及时间锁协议的主要挑战](https://bitcoinops.org/en/newsletters/2018/12/04/#cpfp-carve-out)
* [对于 BIP322 通用签名消息，如何支持时间锁不清楚](https://bitcoinops.org/en/newsletters/2018/09/18/#bip322-generic-signed-message-format)

## 参见

* [HTLCs（哈希时间锁合约）](https://bitcoinops.org/en/topics/htlc/)
* [PTLCs（点时间锁合约）](https://bitcoinops.org/en/topics/ptlc/)
