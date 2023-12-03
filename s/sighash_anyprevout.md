---
description: 同时涵盖 SIGHASH_NOINPUT
---

# SIGHASH\_ANYPREVOUT

**SIGHASH\_ANYPREVOUT**是 SIGHASH\_NOINPUT 的更新版本，是一种签名哈希（sighash）方法，其中被花费的 UTXO 的标识符不被签名，允许将签名与任何受类似脚本保护的 UTXO（即使用相同的公钥）一起使用。

对于拟议中的 [eltoo](https://bitcoinops.org/en/topics/eltoo/) 层用于 LN，需要一种 noinput 风格的 sighash。

## 主要代码和文档

* [BIP118](https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki)

## Optech 新闻简报和网站提及

**2023**

* [使用像 OP\_CTV 和 APO 这样的契约来提高 LN 的可扩展性](https://bitcoinops.org/en/newsletters/2023/09/27/#using-covenants-to-improve-ln-scalability)
* [使用 OP\_CSFS 和 OP\_TXHASH 提出的 OP\_CTV 和 APO 的混合方案](https://bitcoinops.org/en/newsletters/2023/08/30/#covenant-mashup-using-txhash-and-csfs)

**2022**

* [BIPs #1367 简化了 BIP118 对 SIGHASH\_ANYPREVOUT 的描述](https://bitcoinops.org/en/newsletters/2022/10/05/#bips-1367)
* [为测试新的比特币核心软件分支以支持 APO](https://bitcoinops.org/en/newsletters/2022/09/28/#bitcoin-implementation-designed-for-testing-soft-forks-on-signet)
* [使用 APO 和信任设置创建驱动链](https://bitcoinops.org/en/newsletters/2022/09/21/#creating-drivechains-with-apo-and-a-trusted-setup)
* [请求激活稍有修改的 APO，而不是（或在）CTV 之前](https://bitcoinops.org/en/newsletters/2022/04/27/#requested)
* [提出 OP\_TXHASH 作为 CTV 和 APO 的替代方案](https://bitcoinops.org/en/newsletters/2022/02/02/#composable-alternatives-to-ctv-and-apo)
* [关于 APO 或其他契约功能如何使 DLC 更加高效的讨论](https://bitcoinops.org/en/newsletters/2022/02/02/#improving-dlc-efficiency-by-changing-script)

**2021**

* [2021 年回顾：SIGHASH\_ANYPREVOUT](https://bitcoinops.org/en/newsletters/2021/12/22/#anyprevout)
* [提出继承标识符的方案作为 `SIGHASH_ANYPREVOUT` 的替代方案](https://bitcoinops.org/en/newsletters/2021/10/06/#proposal-for-transaction-heritage-identifiers)
* [BIPs #943 更新 BIP118 将其命名为 SIGHASH\_ANYPREVOUT 而不是 SIGHASH\_NOINPUT](https://bitcoinops.org/en/newsletters/2021/07/14/#bips-943)
* [使用 schnorr 签名和 `OP_CAT` 来模拟 `SIGHASH_ANYPREVOUT`](https://bitcoinops.org/en/newsletters/2021/02/03/#replicating-op-checksigfromstack-with-bip340-and-op-cat)

**2020**

* [关于不同主题的讨论，包括 `SIGHASH_ANYPREVOUT`](https://bitcoinops.org/en/newsletters/2020/08/05/#sydney-meetup-discussion)
* [请求替换 BIP118 为 `SIGHASH_ANYPREVOUT` 方案](https://bitcoinops.org/en/newsletters/2020/07/15/#bip118-update)
* [Coinpool：使用 SIGHASH\_NOINPUT 帮助创建支付池](https://bitcoinops.org/en/newsletters/2020/06/17/#coinpool-generalized-privacy-for-identifiable-onchain-protocols)
* [SIGHASH\_NOINPUT 和 eltoo 对 LN 备份的影响](https://bitcoinops.org/en/newsletters/2020/06/03/#ln-backups)
* [对 `SIGHASH_ANYPREVOUTANYSCRIPT` 进行修改以提高 eltoo 灵活性](https://bitcoinops.org/en/newsletters/2020/01/29/#layered-commitments-with-eltoo)

**2019**

* [2019 年回顾：`SIGHASH_ANYPREVOUT`](https://bitcoinops.org/en/newsletters/2019/12/28/#anyprevout)
* [继续讨论 noinput/anyprevout](https://bitcoinops.org/en/newsletters/2019/10/09/#continued-discussion-about-noinput-anyprevout)
* [对 `SIGHASH_ANYPREVOUT` 的批评和一种通用的替代方案](https://bitcoinops.org/en/newsletters/2019/05/29/#not-generic-enough)
* [新提出的 `SIGHASH_ANYPREVOUT` 模式](https://bitcoinops.org/en/newsletters/2019/05/21/#proposed-anyprevout-sighash-modes)
* [关于增加 `SIGHASH_NOINPUT_UNSAFE` 安全性的讨论](https://bitcoinops.org/en/newsletters/2019/03/19/#more-discussion-about-sighash-noinput-unsafe)
* [标记输出以增加 `SIGHASH_NOINPUT_UNSAFE` 的安全性](https://bitcoinops.org/en/newsletters/2019/02/19/#discussion-about-tagging-outputs-to-enable-restricted-features-on-spending)
* [`SIGHASH_NOINPUT_UNSAFE` 的边缘情况](https://bitcoinops.org/en/newsletters/2019/01/08/#continued-sighash-discussion)

**2018**

* [2018 年回顾：`SIGHASH_NOINPUT`](https://bitcoinops.org/en/newsletters/2018/12/28#sighash\_noinput)
* [提议在签名哈希中包含额外数据](https://bitcoinops.org/en/newsletters/2018/11/27/#sighash-updates)
* [关于脚本演变的讨论：`SIGHASH_NOINPUT_UNSAFE`](https://bitcoinops.org/en/newsletters/2018/10/09/#discussion-the-evolution-of-bitcoin-script)
* [将 `SIGHASH_NOINPUT` 重命名为 `SIGHASH_NOINPUT_UNSAFE`](https://bitcoinops.org/en/newsletters/2018/07/17/#naming-of-sighash-noinput)

## 参见

* [Eltoo](https://bitcoinops.org/en/topics/eltoo/)
* [契约（Covenants）](https://bitcoinops.org/en/topics/covenants/)
