# OP\_CODESEPARATOR

**OP\_CODESEPARATOR** 是一个操作码，用于更改签名在提交脚本时使用的数据。该操作码自比特币脚本最初版本以来一直可用，但其使用和行为随时间发生了变化（并且已提出进一步的更改）。

在比特币 0.1 中，用于花费的 scriptSig 和所花费输出的 scriptPubKey 一起评估，中间放置了一个[虚拟](https://github.com/trottier/original-bitcoin/blob/master/src/script.cpp#L1108)的 `OP_CODESEPARATOR`。例如，使用 P2PK 脚本：

`<signature> OP_CODESEPARATOR <public key> OP_CHECKSIG`

在传统比特币脚本中，如上例所示，`OP_CODESEPARATOR` 会从 _scriptCode_ 中移除自身和脚本的任何先前部分——scriptCode 是比特币中用于创建签名所签署的消息的数据的一部分。上述代码分隔符允许签名仅提交到脚本的 `<pubkey> OP_CHECKSIG` 部分。这种操作是必需的，因为签名不能提交给自身——尽管比特币 0.1 还直接使用名为 `FindAndDelete()` 的函数从承诺中移除任何签名。

有[猜测](https://bitcointalk.org/index.php?topic=255145.msg2773654#msg2773654)认为代码分隔符也是早期比特币设计的一部分，可能允许币委托。例如，Alice 拥有一个币，但将 Bob 添加到可以花费它的人员集合中——没有 Alice 交出她的私钥或创建链上交易。Bob 可以通过将 Carol 添加到允许花费者的集合中来进一步委托。没有发布版本的比特币支持这个功能，但声称来自比特币预发布版本的源代码 [可能](https://bitcointalk.org/index.php?topic=382374.msg4108968#msg4108968) 有[支持](https://bitcointalk.org/index.php?topic=382374.msg4109755#msg4109755)这个功能。

在[比特币 0.3.7](https://github.com/bitcoin/bitcoin/commit/6ff5f718b6a67797b2b3bab8905d607ad216ee21#diff-8458adcedc17d046942185cb709ff5c3L1135)（2010 年 7 月）中，与 [1 OP\_RETURN](https://bitcoin.stackexchange.com/questions/38037/what-is-the-1-return-bug) 错误相关的一个修复被部署，改变了脚本的评估方式，包括停止使用虚拟 `OP_CODESEPARATOR`。然而，该操作码本身并未改变，脚本继续能够直接包含它。

## 后续变更和提议

[BIP143](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki) 为 2017 年 8 月激活的版本 0（v0）隔离见证的签名验证规则指定了略有不同的 `OP_CODESEPARATOR` 版本。在传统脚本中，`FindAndDelete()` 操作用于从 scriptCode 中删除所有代码分隔符。在隔离见证 v0 中，不再执行 `FindAndDelete()` 操作，因此在最近执行的代码分隔符之后出现在脚本中的任何 `OP_CODESEPARATOR` 操作码都将包含在 scriptCode 中。否则，该操作码的操作方式相同，通过从 scriptCode 中删除其调用的 `OP_CODESEPARATOR` 和脚本的任何先前部分。

截至本文撰写时，提议的 [tapscript](https://bitcoinops.org/en/topics/tapscript/) 软分叉以实现 v1 隔离见证脚本包含了进一步修改的 `OP_CODESEPARATOR`。在 tapscript 中，签名不再提交计算出的 scriptCode；而是通过其在 [taproot](https://bitcoinops.org/en/topics/taproot/) 默克尔树（称为 tapleaf）中的叶子间接提交到执行的脚本。这将使 `OP_CODESEPARATOR` 变得无用，因此在 tapscript 中，签名必须改为提交到最近执行的 `OP_CODESEPARATOR` 的位置（如果没有执行过，则为 0xffffffff）。

同样截至本文撰写时，提议的 [共识清理](https://bitcoinops.org/en/topics/consensus-cleanup-soft-fork/) 软分叉指定禁止在传统比特币脚本中使用 `OP_CODESEPARATOR`。这将防止它被用于过度次数调用相对较慢的 `FindAndDelete()` 操作，这个问题已知会导致交易和区块验证时间过长。这个提议的变更将使花费到使用代码分隔符的脚本的任何资金变得不可用，因此即使没有人已知使用传统 `OP_CODESEPARATOR`，这个提议的变更也受到了一些[批评](https://bitcoinops.org/en/newsletters/2019/03/12/#cleanup-soft-fork-proposal-discussion)。目前尚不清楚这部分提议是否会被更改。

此外，比特币核心 0.16.1 及更高版本将不会中继或挖掘在传统脚本中使用 `OP_CODESEPARATOR` 的任何交易。

## 主要代码和文档

* [BIP143（无 FindAndDelete）](https://github.com/bitcoin/bips/blob/master/bip-0143.mediawiki#No\_FindAndDelete)
* [BIP341（交易摘要）](https://github.com/bitcoin/bips/blob/master/bip-0341.mediawiki#common-signature-message)
* [共识清理（规范）](https://github.com/TheBlueMatt/bips/blob/cleanup-softfork/bip-XXXX.mediawiki#Specification)

## Optech 新闻简报和网站提及

**2019**

* [关于提议的 tapscript 软分叉的 `OP_CODESEPARATOR` 设计讨论](https://bitcoinops.org/en/newsletters/2019/12/04/#continued-schnorr-taproot-discussion)
* [关于清理软分叉的讨论：关于 `OP_CODESEPARATOR` 的担忧](https://bitcoinops.org/en/newsletters/2019/03/12/#cleanup-soft-fork-proposal-discussion)
* [提议的共识清理软分叉：阻止使用 `OP_CODESEPARATOR`](https://bitcoinops.org/en/newsletters/2019/03/05/#prevent-use-of-op-codeseparator-and-findanddelete-in-legacy-transactions)
* [共识清理背景：传统交易验证](https://bitcoinops.org/en/newsletters/2019/03/05/#legacy-transaction-verification)
* [未来 Script 语言升级中是否应该包含 `OP_CODESEPARATOR`？](https://bitcoinops.org/en/newsletters/2019/01/08/#continued-sighash-discussion)

**2018**

* [Bitcoin Core 0.16.1 停止中继使用 `OP_CODESEPARATOR` 的交易](https://bitcoinops.org/en/newsletters/2018/06/08/#check-for-use-of-the-codeseparator-opcode)

## 参见

* [Tapscript 软分叉提议](https://bitcoinops.org/en/topics/tapscript/)
* [共识清理软分叉提议](https://bitcoinops.org/en/topics/consensus-cleanup-soft-fork/)
