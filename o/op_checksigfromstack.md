# OP\_CHECKSIGFROMSTACK

**OP\_CHECKSIGFROMSTACK (OP\_CSFS)** 是 ElementsProject.org 基于侧链的操作码，有时被提议在比特币上实现。该操作码允许检查一个签名是否签署了任意消息。该操作码接受三个参数：签名、消息和公钥。

比特币现有的签名检查操作码，如 `OP_CHECKSIG`，不允许指定任意消息。它们使用的消息是从执行签名检查操作码的交易中派生的。这使它们能够验证签名是否匹配某个公钥，并且用于生成这两个对象的私钥是否用于授权支出。这种机制足以保护比特币 UTXOs，但它排除了在比特币系统中使用数字签名来认证其他类型数据的可能性。使用 `OP_CSFS` 验证任意消息的能力可以为比特币用户启用几个新功能：

*   **支付签名：**如果 Alice 控制一个私钥，可以签署支付给 Bob 的交易，Bob 可以使用 OP\_CSFS 来无信任地提出支付 Alice 他需要的签名的费用。

    最近，涉及支付签名的协议通常[假设使用适配器签名](https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-July/002077.html)，这些签名更加私密，且占用更少的区块空间。
*   **委托：**Alice 可能想要委托她的币的花费权给 Bob，而不是显式创建一个将币转移到她和 Bob 之间的 1-of-2 多签名的链上交易。如果 Alice 考虑到这种委托，她可以在消息中放入 Bob 的公钥，并使用 OP\_CSFS 来证明她已将花费权委托给该密钥。

    一个更私密、更灵活、更节省区块空间的替代方法是[graftroot](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-February/015700.html)，尽管这需要一个迄今为止只有轻微讨论的软分叉。
*   **预言机：** 一个预言机可能同意签署一个指示事件结果的消息，例如赢得体育赛事的国家队的名字。然后两个或更多用户可以将资金存入使用 OP\_CSFS 的脚本中，根据预言机指示的获胜队伍向不同的人支付。

    最近对预言机调节合约的关注涉及使用[离散对数合约](https://dci.mit.edu/smart-contracts)（DLCs），这些合约可以更加私密和节省区块空间。
*   **双重花费保护债券：**一项服务可能承诺永远不会尝试双重花费其 UTXO，以鼓励其付款人将其未确认交易视为可靠支付。为了展示其诚意，该服务可以使用 OP\_CSFS 提供支付债券的报酬给任何能证明同一密钥被用于创建用于花费同一 UTXO 的两个不同交易的签名的用户。

    这种使用 `OP_CSFS` 的方法可以与 [单次展示签名](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2014-December/007038.html) 进行比较，后者允许任何看到同一密钥的两个签名的人推导出用于创建它们的私钥，从而允许他们花费由该密钥保护的任何其他资金。
*   **交易内省：**如果相同的公钥和签名对在 `OP_CSFS` 和 `OP_CHECKSIG` 下都有效，那么传递给 `OP_CSFS` 的任意消息的内容与隐式用于 `OP_CHECKSIG` 的序列化花费交易（和其他数据）相同。这使得将验证过的花费交易副本放在脚本评估堆栈上成为可能，其他操作码可以在其上运行测试，以强制实施对花费交易的限制。

    例如，如果 `OP_CSFS` 在 2015 年和 2016 年可用，就可以实现 [BIP65](https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki) `OP_CHECKLOCKTIMEVERIFY`（CLTV）和 [BIP112](https://github.com/bitcoin/bips/blob/master/bip-0112.mediawiki) `OP_CHECKSEQUENCEVERIFY`（CSV）的功能，而无需任何共识更改，只需编写验证脚本。

    展望未来，`OP_CSFS` 还可以允许脚本 [实现](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-May/016946.html) 提议的 [SIGHASH\_ANYPREVOUT](https://bitcoinops.org/en/topics/sighash\_anyprevout/) 签名哈希的功能，以及其他操作码提案，如 [OP\_CHECKTEMPLATEVERIFY](https://bitcoinops.org/en/topics/op\_checktemplateverify/)。此外，`OP_CSFS` 将允许创建[契约](https://bitcoinops.org/en/topics/covenants/)，限制一组比特币的花费方式——例如，[金库](https://bitcoinops.org/en/topics/vaults/) 可以限制其花费交易为一小组可接受的 scriptPubKeys，以降低被盗风险。

    `OP_CSFS` 的优势在于它以完全通用的方式提供对签名交易的完整内省。其弱点在于它需要在堆栈上添加一份完整的签名交易副本，这可能显著增加希望使用 `OP_CSFS` 进行内省的交易的大小。相比之下，单一目的内省操作码如 CLTV 和 CSV 使用最小开销，但添加每个新的特殊内省操作码都需要共识更改，即使它们变得不受欢迎，也可能不可能禁用它们的使用，以免有人因此丢失资金。

## 与 OP\_CAT 的关系

向比特币添加 `OP_CSFS` 的提议通常与恢复 `OP_CAT` 操作码的提议结合在一起。`OP_CAT` 操作码在回应 [价值溢出事件](https://en.bitcoin.it/wiki/Value\_overflow\_incident) 的一部分中被 [移除](https://github.com/bitcoin/bitcoin/commit/4bd188c4383d6e614e18f79dc337fbabe8464c82#diff-8458adcedc17d046942185cb709ff5c3R94)。该操作码[连接](https://english.stackexchange.com/questions/125416/concatenate-vs-catenate) 两个元素，将一个附加到另一个上。这使得通过将消息的各个部分（例如交易的字段）连接在一起来构造消息（如序列化交易）成为可能。在堆栈上已经将消息分割成部分进行初始化，简化了对这些部分进行测试的脚本的编写。除了向比特币添加任何新共识代码的基本风险外，没有发表的缺点用于添加 `OP_CAT`。

## 主要代码和文档

* [ElementsProject.org 中的 OP\_CHECKSIGFROMSTACK 代码](https://github.com/ElementsProject/elements/blob/f08447909101bfbbcaf89e382f55c87b2086198a/src/script/interpreter.cpp#L1399)

## Optech 新闻简报和网站提及

**2023**

* [使用 OP\_CSFS 和 OP\_TXHASH 提出的 OP\_CTV 和 APO 的混合](https://bitcoinops.org/en/newsletters/2023/08/30/#covenant-mashup-using-txhash-and-csfs)
* [使用 OP\_CSFS + OP\_CAT 可在链上强制执行过时备份状态的欺诈证明](https://bitcoinops.org/en/newsletters/2023/08/23/#fraud-proofs-for-outdated-backup-state)
* [使用 MATT 提案加上 OP\_CAT 管理联合池的示例](https://bitcoinops.org/en/newsletters/2023/06/07/#using-matt-to-replicate-ctv-and-manage-joinpools)

**2022**

* [可与 `OP_CHECKSIGFROMSTACK` 组合的 `OP_TX` 操作码提议](https://bitcoinops.org/en/newsletters/2022/02/16/#simplified-alternative-to-op-txhash)

**2021**

* [关于 `OP_CHECKSIGFROMSTACK` 设计建议的呼吁](https://bitcoinops.org/en/newsletters/2021/07/14/#request-for-op-checksigfromstack-design-suggestions)
* [使用 Schnorr 签名和 `OP_CAT` 复制 `OP_CHECKSIGFROMSTACK`](https://bitcoinops.org/en/newsletters/2021/02/03/#replicating-op-checksigfromstack-with-bip340-and-op-cat)

**2019**

* [潜在脚本更改的讨论，包括 `OP_CSFS`](https://bitcoinops.org/en/newsletters/2019/06/12/#potential-script-changes)
* [对 `OP_COSHV` 和 `SIGHASH_ANYPREVOUT` 的批评；`OP_CSFS` 作为替代方案](https://bitcoinops.org/en/newsletters/2019/05/29/#not-generic-enough)

**2018**

* [讨论：比特币脚本的演变，`OP_CSFS` 讨论](https://bitcoinops.org/en/newsletters/2018/10/09/#op-checksigfromstack)

## 参见

* [Elements Alpha 中的契约](https://blockstream.com/2016/11/02/en-covenants-in-elements-alpha/)
* [契约](https://bitcoinops.org/en/topics/covenants/)
