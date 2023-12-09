# CPFP 切割 - CPFP Carve Out

**CPFP 切割**是比特币核心中实现的一种交易中继策略，它允许单个交易在仅有一个未确认的祖先时适度超出节点的最大包大小和深度限制。

这使得双方合约协议（如当前的闪电网络协议）能够确保双方都有机会使用 Child Pays For Parent（CPFP）费用提升。第一方可以使用费用提升直至包限制，但不能[固定（pin）](https://bitcoinops.org/en/topics/transaction-pinning/) 交易，因为第二方能够使用 CPFP 切割。

## 主要代码和文档

* [CPFP 切割提案](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-November/016518.html)
* [Bitcoin Core PR#15681：\[内存池\] 允许每个包多一个单祖先交易](https://github.com/bitcoin/bitcoin/pull/15681)

## Optech 新闻简报和网站提及

**2021**

* [研究多方合约协议中费用提升的替代 CPFP 切割方案](https://bitcoinops.org/en/newsletters/2021/12/08/#fee-bumping-research)

**2019**

* [Bitcoin Core 0.19 发布，包含 CPFP 切割](https://bitcoinops.org/en/newsletters/2019/11/27/#cpfp-carve-out)
* [关于使用 CPFP 切割的 LN 锚定输出的持续讨论](https://bitcoinops.org/en/newsletters/2019/11/06/#continued-discussion-of-ln-anchor-outputs)
* [使用 CPFP 切割的 LN 简化承诺](https://bitcoinops.org/en/newsletters/2019/10/30/#ln-simplified-commitments)
* [Bitcoin Core #16421 合并，允许切割被 RBF 替换](https://bitcoinops.org/en/newsletters/2019/09/11/#bitcoin-core-16421)
* [Bitcoin Core #15681 合并，包含 CPFP 切割](https://bitcoinops.org/en/newsletters/2019/07/24/#bitcoin-core-15681)
* [提议覆盖一些 BIP125 条件，替代切割方案](https://bitcoinops.org/en/newsletters/2019/06/12/#proposal-to-override-some-bip125-rbf-conditions)

**2018**

* [CPFP 切割提案](https://bitcoinops.org/en/newsletters/2018/12/04/#cpfp-carve-out)

## 参见

* [交易固定（Transaction pinning）](https://bitcoinops.org/en/topics/transaction-pinning/)
* [锚定输出（Anchor outputs）](https://bitcoinops.org/en/topics/anchor-outputs/)
* [第 3 版交易中继（Version 3 transaction relay）](https://bitcoinops.org/en/topics/version-3-transaction-relay/)
* [Bitcoin Core #16421 允许 RBF 替换切割](https://github.com/bitcoin/bitcoin/pull/16421)
