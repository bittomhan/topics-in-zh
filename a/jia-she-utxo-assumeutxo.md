# 假设 UTXO（AssumeUTXO）

**假设 UTXO（AssumeUTXO）**是一种提出的用于引导新的完整节点的模式，它允许节点推迟验证旧的区块链历史记录，直到用户能够接收到最近的交易。

在节点的代码中，将内嵌一个特定最近时间点所有可花费比特币及其花费条件（UTXO 集合）的哈希。类似于现有的 [assumevalid](https://bitcoincore.org/en/2017/03/08/release-0.14.0/#assumed-valid-blocks) 设置和其他用于节点达成共识的参数，assumeutxo 哈希的修订将在代码审查过程中由开发人员检查其正确性。这将允许新节点的运营者选择性地信任该哈希，并下载与该哈希匹配的 UTXO 集合。对于在 UTXO 集合哈希之后产生的区块，节点将验证新区块并像其他节点一样更新它们自己的 UTXO 集合，无需进一步信任。按照目前的设计，节点还会在后台下载并验证旧区块，以便最终证明它最初开始的哈希是正确的。

## 主要代码和文档

* [假设 UTXO 提案](https://github.com/jamesob/assumeutxo-docs/tree/2019-04-proposal/proposal)
* [假设 UTXO 项目跟踪器](https://github.com/bitcoin/bitcoin/pull/27596)

## Optech 新闻简报和网站提及

**2023**

* [在计算 UTXO 集合哈希时发现的比特币核心错误](https://bitcoinops.org/en/newsletters/2023/10/25/#bitcoin-utxo-set-summary-hash-replacement)
* [Bitcoin Core #27596 添加了假设有效的快照链状态和后台完整验证同步](https://bitcoinops.org/en/newsletters/2023/10/11/#bitcoin-core-27596)
* [Bitcoin Core 开发者面对面会议的总结](https://bitcoinops.org/en/newsletters/2023/05/17/#summaries-of-bitcoin-core-developers-in-person-meeting)
* [Bitcoin Core #25740 允许后台验证引导 UTXO 状态](https://bitcoinops.org/en/newsletters/2023/03/15/#bitcoin-core-25740)

**2021**

* [Bitcoin Core #23155 扩展了 `dumptxoutset` RPC，增加了新信息](https://bitcoinops.org/en/newsletters/2021/12/08/#bitcoin-core-23155)
* [Bitcoin Core #19521 简化了为旧区块生成 UTXO 集合哈希的过程](https://bitcoinops.org/en/newsletters/2021/05/05/#bitcoin-core-19521)
* [为跟踪 UTXO 状态哈希添加了 MuHash 函数](https://bitcoinops.org/en/newsletters/2021/01/13/#bitcoin-core-19055)

**2020**

* [MuHash 实现快速哈希 UTXO 集合的 Review Club 总结](https://bitcoinops.org/en/newsletters/2020/11/11/#bitcoin-core-pr-review-club)

**2019**

* [2019 年回顾：假设 UTXO](https://bitcoinops.org/en/newsletters/2019/12/28/#assumeutxo)
* [CoreDev.tech 展示和讨论假设UTXO](https://bitcoinops.org/en/newsletters/2019/06/12/#assume-utxo-demo)
* [关于假设有效机制对UTXO快照的讨论](https://bitcoinops.org/en/newsletters/2019/04/09/#discussion-about-an-assumed-valid-mechanism-for-utxo-snapshots)

## 参见

* [Bitcoin Core 问题 #15605: 假设 UTXO 讨论](https://github.com/bitcoin/bitcoin/issues/15605)
* [\[bitcoin-dev\] 假设 UTXO 和 UTXO 快照](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-April/016825.html)
