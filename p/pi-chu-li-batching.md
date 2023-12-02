---
description: 同时涵盖批处理（Batching）
---

# 支付批处理 - Payment Batching

**支付批处理（Payment Batching）**是将多个支付包含在同一链上交易中的技术。这种方法分摊了创建交易、消费输入和创建找零输出的成本，使得交易中所有支付的平均成本降低。

通过仅批处理少量支付，就有可能在不降低确认速度或不需要其他更改的情况下，节省 75% 的交易费用。即使使用与不进行批处理时相同的输入，也有可能节省超过 20% 的费用。

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## 主要代码和文档

* [使用支付批处理扩展比特币](https://bitcoinops.org/en/payment-batching/)

## Optech 新闻简报和网站提及

**2023 年**

* [提议的 `OP_VAULT` 操作码支持批量提取保险库](https://bitcoinops.org/en/newsletters/2023/01/18/#proposal-for-new-vault-specific-opcodes)

**2021 年**

* [基于候选集的区块模板可能有助于提升批处理支付的费用提升](https://bitcoinops.org/en/newsletters/2021/06/02/#candidate-set-based-csb-block-template-construction)

**2020 年**

* [BOLTs #803 增加了使用批次安全结算 HTLCs 的建议](https://bitcoinops.org/en/newsletters/2020/12/16/#bolts-803)
* [Sparrow 钱包增加了支付批处理支持](https://bitcoinops.org/en/newsletters/2020/11/18/#sparrow-wallet-adds-payment-batching-and-payjoin)
* [比特币核心 #16378 为钱包添加了一个支持批处理的新 RPC](https://bitcoinops.org/en/newsletters/2020/09/23/#bitcoin-core-16378)
* [C-Lightning #3812 为其链上钱包增加了批处理支持](https://bitcoinops.org/en/newsletters/2020/09/16/#c-lightning-3812)
* [C-Lightning #3763 添加了批量开放通道的新 RPC](https://bitcoinops.org/en/newsletters/2020/09/16/#c-lightning-3763)
* [Specter 桌面增加了支付批处理支持](https://bitcoinops.org/en/newsletters/2020/08/19/#specter-desktop-adds-batching)
* [实地报告：批处理如何节省数百万美元的费用](https://bitcoinops.org/en/veriphi-segwit-batching/)
* [Coinbase 的提现交易现在使用支付批处理](https://bitcoinops.org/en/newsletters/2020/03/18/#coinbase-withdrawal-transactions-now-using-batching)
* [关于压缩支付批处理的 OP\_CHECKTEMPLATEVERIFY 讨论](https://bitcoinops.org/en/newsletters/2020/02/12/#op-checktemplateverify-ctv-workshop)
* [不等值的 CoinJoin 可能看起来像批处理，以改善隐私](https://bitcoinops.org/en/newsletters/2020/01/08/#coinjoins-without-equal-value-inputs-or-outputs)

**2019 年**

* [提议新的操作码以在费用高峰期更有效地进行批处理](https://bitcoinops.org/en/newsletters/2019/05/29/#proposed-transaction-output-commitments)
* [演讲：回归费用，涵盖包括批处理在内的技术](https://bitcoinops.org/en/newsletters/2019/05/29/#presentation-a-return-to-fees)

**2018 年**

* [2018 年回顾：约 11% 的支付使用了批处理](https://bitcoinops.org/en/newsletters/2018/12/28/#batched-payments)

## 参见

* [OP\_CHECKTEMPLATEVERIFY](https://bitcoinops.org/en/topics/op\_checktemplateverify/)

