# 第三版交易中继 - Version 3 Transaction Relay

**第三版交易中继**是一项提案，允许交易选择加入一组修改后的交易中继策略，旨在防止固定攻击（pinning attacks）。结合包中继（package relay），这些策略有助于启用 LN 链上交易的动态手续费率。

第三版交易中继是标准交易策略的超集。也就是说，v3 交易遵循所有标准交易的规则（例如最小和最大交易重量），同时增加了一些额外的规则，旨在允许[交易替换](https://bitcoinops.org/en/topics/replace-by-fee/)，同时阻止交易固定攻击。v3 交易还需要对[包替换费](https://bitcoinops.org/en/topics/package-relay/)策略进行轻微的修改，以保持与矿工的激励兼容。

第三版交易中继解决了规则 3 [交易固定](https://bitcoinops.org/en/topics/transaction-pinning/)的问题，并可能允许移除 [CPFP carve-out](https://bitcoinops.org/en/topics/cpfp-carve-out/)。

版本 3 交易被[短暂锚点](https://bitcoinops.org/en/topics/ephemeral-anchors/)所使用。

## 主要代码和文档

* [新的交易策略 (nVersion=3) 用于合约协议](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-September/020937.html)

## Optech 新闻简报和网站提及

**2023**

* [当前 v3 交易中继策略无法解决的循环替换攻击](https://bitcoinops.org/en/newsletters/2023/10/25/#replacement-cycling-vulnerability-against-htlcs)
* [闪电网络开发者讨论多个中继策略主题，包括 v3 交易中继](https://bitcoinops.org/en/newsletters/2023/07/26/#reliable-transaction-confirmation)
* [使用 v3 交易中继防止硬币混合固定](https://bitcoinops.org/en/newsletters/2023/06/28/#preventing-coinjoin-pinning-with-v3-transaction-relay)

**2022**

* [2022 年回顾：v3 交易中继](https://bitcoinops.org/en/newsletters/2022/12/21/#v3-tx-relay)
* [短暂锚点实现作为 v3 交易中继策略的提议扩展](https://bitcoinops.org/en/newsletters/2022/12/07/#ephemeral-anchors-implementation)
* [比较禁用不可替换交易与禁用特殊 v3 交易中继规则](https://bitcoinops.org/en/newsletters/2022/11/09/#determining-incentive-compatibility-isn-t-always-straightforward)
* [基于 v3 交易中继提案的短暂锚点提议](https://bitcoinops.org/en/newsletters/2022/10/26/#ephemeral-anchors)
* [针对 LN 惩罚设计的新交易中继策略提案](https://bitcoinops.org/en/newsletters/2022/10/05/#proposed-new-transaction-relay-policies-designed-for-ln-penalty)

## 参见

* [交易固定](https://bitcoinops.org/en/topics/transaction-pinning/)
* [短暂锚点](https://bitcoinops.org/en/topics/ephemeral-anchors/)
