# 契约 - Covenants



**契约**是比特币共识规则的一类提议更改，这些更改将允许脚本阻止授权花费者将资金支付给特定其他脚本。

> “在比特币的背景下，契约最有用的定义是，当一个 UTXO 的 scriptPubKey 限制了花费该 UTXO 的交易的输出中的 scriptPubKey 时。” —Anthony Towns（来源）

例如，一个契约通常只允许将资金支付给一个白名单的脚本集合，比如将比特币返回给用户自己的余额，或支付给一个仅在一段时间后允许支付到任意地址的暂存地址。

## 主要代码和文档

* [通过契约增强比特币交易](https://fc17.ifca.ai/bitcoin/papers/bitcoin17-final28.pdf)

## Optech 新闻简报和网站提及

**2023**

* [使用契约进行 HTLC 聚合](https://bitcoinops.org/en/newsletters/2023/11/08/#htlc-aggregation-with-covenants)
* [研究用于输出脚本内省的最小操作码以启用契约](https://bitcoinops.org/en/newsletters/2023/10/25/#research-into-generic-covenants-with-minimal-script-language-changes)
* [提议的 `OP_TXHASH` BIP 规范草案](https://bitcoinops.org/en/newsletters/2023/10/11/#specification-for-op-txhash-proposed)
* [使用像 OP\_CTV 和 APO 这样的契约提高 LN 可扩展性](https://bitcoinops.org/en/newsletters/2023/09/27/#using-covenants-to-improve-ln-scalability)
* [提议使用 OP\_CSFS 和 OP\_TXHASH 混合 OP\_CTV 和 APO](https://bitcoinops.org/en/newsletters/2023/08/30/#covenant-mashup-using-txhash-and-csfs)
* [Ark 的提议联合池构造可以通过契约减少交互](https://bitcoinops.org/en/newsletters/2023/05/31/#proposal-for-a-managed-joinpool-protocol)
* [使用 MATT 风格契约的 `OP_VAULT` 替代设计分析](https://bitcoinops.org/en/newsletters/2023/05/03/#matt-based-vaults)
* [受 `OP_TLUV` 启发的 `OP_VAULT` 替代设计提案](https://bitcoinops.org/en/newsletters/2023/03/08/#alternative-design-for-op-vault)
* [提议 `OP_VAULT` 和 `OP_UNVAULT` 操作码以启用基于契约的保险库](https://bitcoinops.org/en/newsletters/2023/01/18/#proposal-for-new-vault-specific-opcodes)

**2022**

* [提议使用契约和默克尔树启用通用智能合约](https://bitcoinops.org/en/newsletters/2022/11/16/#general-smart-contracts-in-bitcoin-via-covenants)
* [关于递归契约带来的矿工可提取价值（MEV）风险的讨论](https://bitcoinops.org/en/newsletters/2022/05/25/#miner-extractable-value-discussion)
* [启用 `OP_CAT` 时何时允许递归契约？](https://bitcoinops.org/en/newsletters/2022/05/18/#when-would-enabling-op-cat-allow-recursive-covenants)
* [更新的 `OP_TX` 操作码有助于构建契约](https://bitcoinops.org/en/newsletters/2022/05/18/#updated-op-tx-proposal)
* [关于允许递归契约的风险讨论](https://bitcoinops.org/en/newsletters/2022/03/09/#limiting-script-language-expressiveness)
* [提议的 `OP_EVICT` 操作码使契约更高效](https://bitcoinops.org/en/newsletters/2022/03/02/#proposed-opcode-to-simplify-shared-utxo-ownership)- [提议可组合的 `OP_TX` 操作码以构建契约](https://bitcoinops.org/en/newsletters/2022/02/16/#simplified-alternative-to-op-txhash)

**2021**

* [提议 OP\_TAPLEAF\_UPDATE\_VERIFY 操作码与 Taproot 原生契约设计](https://bitcoinops.org/en/newsletters/2021/09/15/#covenant-opcode-proposal)
* [使用 `OP_CAT` 和 Schnorr 签名复制 `OP_CSFS` 启用契约的操作码](https://bitcoinops.org/en/newsletters/2021/02/03/#replicating-op-checksigfromstack-with-bip340-and-op-cat)

**2020**

* [讨论 Simplicity 如何用于契约](https://bitcoinops.org/en/newsletters/2020/08/05/#bip-taproot)
* [多重签名保险库契约原型的演示实现](https://bitcoinops.org/en/newsletters/2020/04/29/#multiparty-vault-architecture)
* [使用预签名交易的保险库原型](https://bitcoinops.org/en/newsletters/2020/04/22/#vaults-prototype)
* [OP\_CHECKTEMPLATEVERIFY 研讨会报告](https://bitcoinops.org/en/newsletters/2020/02/12/#op-checktemplateverify-ctv-workshop)

**2019**

* [2019 年度回顾：OP\_CHECKTEMPLATEVERIFY](https://bitcoinops.org/en/newsletters/2019/12/28/#ctv)
* [OP\_CHECKTEMPLATEVERIFY 提案的建议更改](https://bitcoinops.org/en/newsletters/2019/12/18/#proposed-changes-to-bip-ctv)
* [OP\_CHECKOUTPUTSHASHVERIFY 重命名为 OP\_CHECKTEMPLATEVERIFY 并更新](https://bitcoinops.org/en/newsletters/2019/12/04/#op-checktemplateverify-ctv)
* [没有契约的比特币保险库](https://bitcoinops.org/en/newsletters/2019/08/14#bitcoin-vaults-without-covenants)
* [CoreDev.tech 讨论：潜在的脚本更改](https://bitcoinops.org/en/newsletters/2019/06/12/#potential-script-changes)
* [新提议的操作码：OP\_CHECKOUTPUTSHASHVERIFY](https://bitcoinops.org/en/newsletters/2019/05/29/#proposed-new-opcode-for-transaction-output-commitments)

**2018**

* [Scaling Bitcoin Tokyo 2018, Script Roundtable: OP\_CHECKSIGFROMSTACK](https://bitcoinops.org/en/newsletters/2018/10/09/#discussion-the-evolution-of-bitcoin-script)

## 参见

* [比特币中契约的早期描述](https://bitcointalk.org/index.php?topic=278122.0)
* [OP\_CHECKSIGFROMSTACK](https://bitcoinops.org/en/topics/op\_checksigfromstack/)
* [OP\_CHECKTEMPLATEVERIFY](https://bitcoinops.org/en/topics/op\_checktemplateverify/)
* [SIGHASH\_ANYPREVOUT](https://bitcoinops.org/en/topics/sighash\_anyprevout/)
* [保险库（Vaults）](https://bitcoinops.org/en/topics/vaults/)
