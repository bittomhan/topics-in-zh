---
description: 也涵盖支付池（Payment pools）和联合池（Joinpools）
---

# 硬币池 - Coinpools

**联合池**是一种构造，允许多个用户无需信任地共享一个或多个 UTXO（未使用的交易输出）的所有权。当资金被支出时，无法从区块链上判断是哪个联合池成员（或成员们）花费了这些资金。联合池可以使用预签名的交易或提议的协议功能来确保每个成员随时可以单方面从池中提取他们的资金。

_这个话题描述是一个草稿。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/joinpools.md) _提供有关该话题的更多背景信息。_

## Optech 新闻简报和网站提及

**2023**

* [使用 MATT 提案加上 OP\_CAT 来管理联合池的示例](https://bitcoinops.org/en/newsletters/2023/06/07/#using-matt-to-replicate-ctv-and-manage-joinpools)
* [Ark 管理联合池协议的提案](https://bitcoinops.org/en/newsletters/2023/05/31/#proposal-for-a-managed-joinpool-protocol)

**2022**

* [提出的 `OP_EVICT` 操作码以使联合池更高效](https://bitcoinops.org/en/newsletters/2022/03/02/#proposed-opcode-to-simplify-shared-utxo-ownership)

**2021**

* [Taproot 软分叉后的想法：OP\_TAPLEAF\_UPDATE\_VERIFY](https://bitcoinops.org/en/newsletters/2021/10/27/#op-tapleaf-update-verify)
* [OP\_TAPLEAF\_UPDATE\_VERIFY 提案以简化契约和联合池的实现](https://bitcoinops.org/en/newsletters/2021/09/15/#covenant-opcode-proposal)

**2020**

* [CoinPool：可识别链上协议的通用隐私](https://bitcoinops.org/en/newsletters/2020/06/17/#coinpool-generalized-privacy-for-identifiable-onchain-protocols)

## 参见

* [Coinjoin（币混合）](https://bitcoinops.org/en/topics/coinjoin/)
* [通道工厂（Channel factories）](https://bitcoinops.org/en/topics/channel-factories/)
* [契约（Covenants）](https://bitcoinops.org/en/topics/covenants/)
