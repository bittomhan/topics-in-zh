---
description: 同时涵盖子支付父（Child Pays For Parent, CPFP）
---

# 祖先费率挖矿 - Ancestor Feerate Mining

**子支付父（Child Pays For Parent, CPFP）** 是一种费用提升技术，用户通过在子交易中以高费率花费一个低费率未确认交易的输出，从而鼓励矿工在一个区块中包含这两个交易。

比特币的共识规则要求创建输出的交易必须在区块链中比使用该输出的交易更早出现——包括如果两者都包含在同一区块中，父交易必须出现在子交易之前。

这意味着，一个未确认且费率高的交易可以激励矿工挖掘其任何也未确认的祖先交易。例如比特币核心（Bitcoin Core）这样实现此类交易选择策略的节点，为其区块模板称之为_祖先费率挖矿（ancestor feerate mining）_。只要有一定比例的矿工实现祖先费率挖矿，钱包就可以使用CPFP作为费用提升技术。

## 主要代码与文档

* [比特币核心的内存池和挖矿](https://github.com/bitcoin-core/bitcoin-devwiki/wiki/Mempool-and-mining)
* [Bitcoin Core #7600：祖先费率挖矿](https://github.com/bitcoin/bitcoin/pull/7600)

## Optech 新闻稿和网站提及

**2023年**

* [使用非可塑性交易 ID 为 CPFP 创建任何人可支付输出](https://bitcoinops.org/en/newsletters/2023/11/15/#eliminating-malleability-from-ephemeral-anchor-spends)
* [CPFP 或 RBF 对之前的 CPFP 费用提升的建议最佳实践](https://bitcoinops.org/en/newsletters/2023/04/26/#best-practices-with-multiple-cpfps-cpfp-rbf)

**2022年**

* [建议 LN 提供替代方案以避免使用 CPFP 进行大多数 HTLC 费用提升](https://bitcoinops.org/en/newsletters/2022/11/02/#anchor-outputs-workaround)
* [建议使用 CPFP 解决与 RBF 相关的免费选择问题](https://bitcoinops.org/en/newsletters/2022/10/26/#free-option-problem)
* [为使 CPFP 提升更可靠，提出了打包转发的 BIP 提案](https://bitcoinops.org/en/newsletters/2022/05/25/#package-relay-proposal)
* [Bitcoin Core #24152 开始接受由其子交易支付的低费率交易](https://bitcoinops.org/en/newsletters/2022/04/13/#bitcoin-core-24152)
* [BTCPay Server 1.4.5 添加了对 CPFP 费用提升的支持](https://bitcoinops.org/en/newsletters/2022/03/02/#btcpay-server-1-4-6)

**2021年**

* [在实现打包转发前，提出最初的 CPFP 规则以接受内存池打包](https://bitcoinops.org/en/newsletters/2021/09/22/#package-mempool-acceptance-and-package-rbf)
* [候选集区块模板可能使某些 CPFP 费用提升更有效](https://bitcoinops.org/en/newsletters/2021/06/02/#candidate-set-based-csb-block-template-construction)
* [Sparrow 1.4.0 添加了从交易列表中对 CPFP 费用提升的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#sparrow-1-4-0-released)
* [Bitcoin Core #21359 允许对传入支付进行 CPFP 费用提升](https://bitcoinops.org/en/newsletters/2021/05/19/#bitcoin-core-21359)
* [使用 CPFP 费用提升的 LN 承诺交易的挑战](https://bitcoinops.org/en/newsletters/2021/04/21/#using-anchor-outputs-by-default-in-lnd)

**2020年**

* [Copay 添加了对传入交易进行 CPFP 费用提升的支持](https://bitcoinops.org/en/newsletters/2020/05/20/#copay-enables-cpfp-for-incoming-transactions)

**2019年**

* [为祖先转发准备的重构](https://bitcoinops.org/en/newsletters/2019/09/25/#bitcoin-core-16400)
* [LND #3140 添加了对 RBF 和 CPFP 费用提升清扫交易的支持](https://bitcoinops.org/en/newsletters/2019/06/19/#lnd-3140)

**2018年**

* [提出了 CPFP carve-out](https://bitcoinops.org/en/newsletters/2018/12/04/#cpfp-carve-out)
* [为 LN 简化费用提升](https://bitcoinops.org/en/newsletters/2018/11/27/#simplified-fee-bumping-for-ln)

## 参见

* [CPFP carve-out](https://bitcoinops.org/en/topics/cpfp-carve-out/)
* [打包转发（Package Relay）](https://bitcoinops.org/en/topics/package-relay/)
