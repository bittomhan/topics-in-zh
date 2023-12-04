# 金库 - Vaults

**金库**是一种协议类型，它要求用户从其钱包中花费资金时，需在两个不同的区块中出现两个分开的交易。第一个交易表明有人试图花费这些资金，并给用户机会阻止完成花费的第二个交易。

金库协议规定了两次交易之间必须经过的最小时间或区块数量，给用户足够的时间来注意是否有人偷了他们的私钥并试图盗走他们的资金。如果用户发现盗窃企图，大多数金库设计还允许用户将资金发送到使用更安全脚本的安全地址，或永久销毁资金以防止窃贼从攻击中获利。

一些金库设计依赖于需要比特币共识变更的[契约](https://bitcoinops.org/en/topics/covenants/)。其他金库设计使用现有协议特性以及提前签署交易然后销毁签署其他交易的手段（通过安全删除签名密钥或使用多重签名确保需要泄露多个独立密钥）的技术。

## 主要代码和文档

* [Möser-Eyal-Sirer 金库提案](https://hackingdistributed.com/2016/02/26/how-to-implement-secure-bitcoin-vaults/)
* [使用 OP\_CHECKSIGFROMSTACK 和 OP\_CAT 的金库](https://blockstream.com/2016/11/02/en-covenants-in-elements-alpha/)
* [不改变比特币共识规则的金库](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-August/017229.html)
* [使用比特币金库的托管协议](https://arxiv.org/abs/2005.11776)

## Optech 新闻简报和网站提及

**2023**

* [关于在 taproot 附件中存储金库相关数据的讨论](https://bitcoinops.org/en/newsletters/2023/06/14/#discussion-about-the-taproot-annex)
* [`OP_VAULT` 的替代设计分析，使用 MATT 风格的契约](https://bitcoinops.org/en/newsletters/2023/05/03/#matt-based-vaults)
* [受 `OP_TLUV` 启发的 `OP_VAULT` 替代设计提案](https://bitcoinops.org/en/newsletters/2023/03/08/#alternative-design-for-op-vault)
* [`OP_VAULT` 和 `OP_UNVAULT` 操作码的草案 BIP](https://bitcoinops.org/en/newsletters/2023/02/22/#draft-bip-for-op-vault)
* [`OP_VAULT` 和 `OP_UNVAULT` 操作码的提案](https://bitcoinops.org/en/newsletters/2023/01/18/#proposal-for-new-vault-specific-opcodes)

**2022**

* [提议将简单金库用作比较不同契约设计的一个基准](https://bitcoinops.org/en/newsletters/2022/04/27/#suggested)
* [基于 CTV 的金库设计和代码](https://bitcoinops.org/en/newsletters/2022/03/16/#continued-ctv-discussion)

**2021**

* [金库是否应始终有一个合作的 taproot 密钥路径花费?](https://bitcoinops.org/en/newsletters/2021/10/13/#vaults)
* [提出 `OP_TAPLEAF_UPDATE_VERIFY` 操作码，可简化某些金库设计](https://bitcoinops.org/en/newsletters/2021/09/15/#covenant-opcode-proposal)
* [为 taproot 更新金库](https://bitcoinops.org/en/newsletters/2021/09/08/#preparing-for-taproot-12-vaults-with-taproot)
* [使用 schnorr 签名和 `OP_CAT` 创建金库](https://bitcoinops.org/en/newsletters/2021/02/03/#replicating-op-checksigfromstack-with-bip340-and-op-cat)
* [使硬件钱包与高级功能（如金库）兼容](https://bitcoinops.org/en/newsletters/2021/01/20/#making-hardware-wallets-compatible-with-more-advanced-bitcoin-features)

**2020**

* [2020 年回顾：金库](https://bitcoinops.org/en/newsletters/2020/12/23/#vaults)
* [提出用于存储预签名金库交易的服务](https://bitcoinops.org/en/newsletters/2020/07/01/#proposed-service-for-storing-relaying-and-broadcasting-presigned-transactions)
* [Revault 多方金库架构的介绍](https://bitcoinops.org/en/newsletters/2020/06/03/#the-revault-multiparty-vault-architecture)
* [Revault：多方金库的实现](https://bitcoinops.org/en/newsletters/2020/04/29/#multiparty-vault-architecture)
* [Python 编写的金库原型](https://bitcoinops.org/en/newsletters/2020/04/22/#vaults-prototype)
* [OP\_CHECKTEMPLATEVERIFY (CTV) 研讨会讨论：使用 CTV 与金库](https://bitcoinops.org/en/newsletters/2020/02/12/#op-checktemplateverify-ctv-workshop)

**2019**

* [2019 年回顾：没有契约的金库](https://bitcoinops.org/en/newsletters/2019/12/28/#vaults)
* [比特币金库不使用契约和之前金库提案的弱点](https://bitcoinops.org/en/newsletters/2019/08/14/#bitcoin-vaults-without-covenants)

## 参见

* [Python 金库](https://github.com/kanzure/python-vaults)
* [Revault 多方金库演示](https://github.com/re-vault/revault-demo)
* [Bitcoin 金库](https://github.com/JSwambo/bitcoin-vault)
* [契约](https://bitcoinops.org/en/topics/covenants/)
