# 短暂锚点 - Ephemeral anchors

**短暂锚点**是一个提议，允许某些交易即使不支付任何交易费用也能被转发，前提是它们作为包含支付足够整个包费用的子交易的[交易包（relay package）](https://bitcoinops.org/en/topics/package-relay/) 的一部分被转发。

该提议是建立在 [v3 交易转发](https://bitcoinops.org/en/topics/version-3-transaction-relay/) 提案的基础上。一个包含尽可能少的零费用的 v3 交易，其输出为零值并支付 `OP_TRUE` 作为整个脚本，当包含在一个支付费用的子交易的交易包中时，将被接受。

这允许网络上的任何人使用该输出作为子交易的输入。这允许任何人创建支付费用的子交易，即使他们没有接收父交易的其他输出。这使得短暂锚点可以作为[费用赞助（fee sponsorship）](https://bitcoinops.org/en/topics/fee-sponsorship/) 的功能，但不需要任何共识变更。

短暂锚点被设想用于诸如闪电网络（LN）这样的合约协议，其中交易在广播前很长时间内由合约参与者签署，阻止参与者确定合适的费率。相反，任何参与者（或多个共同行动的参与者）可以使用短暂锚点输出作为子交易的输入，从而在交易广播时增加费用。这类似于 2021-22 年加入 LN 的[锚点输出（anchor outputs）](https://bitcoinops.org/en/topics/anchor-outputs/)，基于 [CPFP carve out](https://bitcoinops.org/en/topics/cpfp-carve-out/) 的转发规则。

## 主要代码和文档

* [短暂锚点](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-October/021036.html)

## Optech 新闻简报和网站提及

**2023**

* [使用非可变交易 ID 进行短暂锚点支出](https://bitcoinops.org/en/newsletters/2023/11/15/#eliminating-malleability-from-ephemeral-anchor-spends)
* [闪电网络开发者关于多个转发政策主题的讨论，包括短暂锚点](https://bitcoinops.org/en/newsletters/2023/07/26/#reliable-transaction-confirmation)
* [比特币审判 #23 添加了对短暂锚点的部分支持](https://bitcoinops.org/en/newsletters/2023/04/26/#bitcoin-inquisition-23)
* [将短暂锚点与 `SIGHASH_GROUP` 进行比较](https://bitcoinops.org/en/newsletters/2023/01/25/#ephemeral-anchors-compared-to-sighash-group)

**2022**

* [短暂锚点实现](https://bitcoinops.org/en/newsletters/2022/12/07/#ephemeral-anchors-implementation)
* [短暂锚点](https://bitcoinops.org/en/newsletters/2022/10/26/#ephemeral-anchors)
* [为 v3 交易转发提出的额外规则，以协助 CPFP 费用增加](https://bitcoinops.org/en/newsletters/2022/10/05/#ephemeral-dust)

## 参见

* [V3 交易转发](https://bitcoinops.org/en/topics/version-3-transaction-relay/)- [锚点输出](https://bitcoinops.org/en/topics/anchor-outputs/)
* [交易包](https://bitcoinops.org/en/topics/package-relay/)
* [费用赞助](https://bitcoinops.org/en/topics/fee-sponsorship/)
* [CPFP carve out](https://bitcoinops.org/en/topics/cpfp-carve-out/)
