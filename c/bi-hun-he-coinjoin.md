# 币混合 - CoinJoin

**币混合**是一种无需信任的协议，用于混合多个所有者的 UTXO（未使用的交易输出），以使外部方难以使用区块链的交易历史来确定谁拥有哪些比特币。

这个名词源于 Gregory Maxwell 在 2013 年的 [提案](https://bitcointalk.org/index.php?topic=279249.0)。自那以后，几个独立的实现支持了各种形式的 CoinJoin。

## 主要代码和文档

* [CoinJoin：现实世界中的比特币隐私](https://bitcointalk.org/index.php?topic=279249.0)
* [Zerolink：比特币可互换性框架](https://github.com/nopara73/ZeroLink)

## Optech 新闻简报和网站提及

**2023**

* [使用 v3 交易中继防止 CoinJoin 定位](https://bitcoinops.org/en/newsletters/2023/06/28/#preventing-coinjoin-pinning-with-v3-transaction-relay)
* [讨论关于中继 taproot annexes 的 CoinJoin 风格协议的风险](https://bitcoinops.org/en/newsletters/2023/06/14/#discussion-about-the-taproot-annex)

**2022**

* [Wasabi 2.0 实现 WabiSabi](https://bitcoinops.org/en/newsletters/2022/04/06/#wabisabi-alternative-to-payjoin)

**2021**

* [Sparrow 1.5.0 添加了 CoinJoin 支持](https://bitcoinops.org/en/newsletters/2021/10/20/#sparrow-adds-coinjoin-support)
* [JoinMarket 0.9.0 发布，实现了用于 CoinJoin 的忠诚度债券以抵抗女巫攻击](https://bitcoinops.org/en/newsletters/2021/08/11/#implementation-of-fidelity-bonds)
* [基于候选集的区块模板可能有助于提高大型 CoinJoin 的费用提升](https://bitcoinops.org/en/newsletters/2021/06/02/#candidate-set-based-csb-block-template-construction)

**2020**

* [WabiSabi：一个用于协调具有任意输出值的 CoinJoin 的协议](https://bitcoinops.org/en/newsletters/2020/06/17/#wabisabi-coordinated-coinjoins-with-arbitrary-output-values)
* [比较 CoinJoin 隐私和 CoinSwap 隐私](https://bitcoinops.org/en/newsletters/2020/06/03/#design-for-a-coinswap-implementation)
* [允许硬件钱包安全地签署自动化 CoinJoin 交易](https://bitcoinops.org/en/newsletters/2020/05/13/#request-for-an-additional-taproot-signature-commitment)
* [Wormhole：一种作为 Chaumian CoinJoin 一部分发送支付的协议](https://bitcoinops.org/en/newsletters/2020/01/22/#new-coinjoin-mixing-technique-proposed)
* [评估没有等值输入或输出的 CoinJoin](https://bitcoinops.org/en/newsletters/2020/01/08/#coinjoins-without-equal-value-inputs-or-outputs)

**2019**

* [2019 年度回顾：SNICKER](https://bitcoinops.org/en/newsletters/2019/12/28/#snicker)
* [简单非交互式 CoinJoin 带加密重用密钥（SNICKER）](https://bitcoinops.org/en/newsletters/2019/09/04/#snicker-proposed)
* [用于改进分布式 CoinJoin 的忠诚度债券提供更好的女巫攻击防御](https://bitcoinops.org/en/newsletters/2019/07/31/#fidelity-bonds-for-improved-sybil-resistance)

**2018**

* [关于 Wasabi 币混合和交易所黑名单的问题](https://bitcoinops.org/en/newsletters/2018/09/25/#how-likely-are-you-to-get-blacklisted-by-an-exchange-if-you-use-wasabi-wallet-s-coinjoin-mixing)- [可能帮助硬件钱包参与 CoinJoin 的 Sighash 更新](https://bitcoinops.org/en/newsletters/2018/09/04/#proposed-sighash-updates)
* [可能有助于非交互式 CoinJoin 的 BLS 签名库](https://bitcoinops.org/en/newsletters/2018/08/07/#library-announced-for-bls-signatures)
* [CoinJoinXT 演示](https://bitcoinops.org/en/newsletters/2018/07/10/#coinjoinxt-and-other-techniques-for-deniable-transfers)

## 参见

* [Payjoin](https://bitcoinops.org/en/topics/payjoin/)
* [CoinJoin（比特币维基：隐私）](https://en.bitcoin.it/Privacy#CoinJoin)
