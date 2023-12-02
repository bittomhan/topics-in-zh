# MuSig

**MuSig** 是一种用于聚合公钥和签名的协议，适用于 Schnorr 数字签名算法。

MuSig 允许多个用户，每个用户都有自己的私钥，创建一个合并的公钥，该公钥与其他任何 Schnorr 公钥无法区分，包括与单用户公钥的大小相同。它进一步描述了如何由创建公钥的用户一起合作，以安全地创建与公钥相对应的 [多重签名](https://bitcoinops.org/en/topics/multisignature/)。与公钥一样，签名与任何其他 Schnorr 签名无法区分。

与传统的基于脚本的多签相比，MuSig 占用更少的区块空间，更加隐私，但它也需要参与者之间更多的互动。截至 2021 年 8 月，MuSig 家族中有三种协议：

* **MuSig**（也称为 MuSig1），应该易于实现，但在签名过程中需要三轮通信。
* **MuSig2**，同样易于实现。它消除了一轮通信，并允许将另一轮与密钥交换结合。这可以允许使用与今天基于脚本的多签类似的签名过程。这确实需要存储额外的数据，并且需要非常小心，确保您的签名软件或硬件不会被欺骗，无意中重复签名会话的一部分。
* **MuSig-DN**（Deterministic Nonce），实现的复杂性显著增加。其参与者之间的通信不能与密钥交换结合，但它的优势在于它不容易受到重复会话攻击的影响。

## 主要代码和文档

* [MuSig 论文](https://eprint.iacr.org/2018/068)
* [MuSig2 论文](https://eprint.iacr.org/2020/1261)
* [MuSig-DN 论文](https://eprint.iacr.org/2020/1057.pdf)

## Optech 新闻简报和网站提及

**2023**

* [MuSig2 在 PSBT 中的字段的提议 BIP](https://bitcoinops.org/en/newsletters/2023/10/18/#proposed-bip-for-musig2-fields-in-psbts)
* [LND #7994 为 MuSig2 协议的远程签名添加了 RPC 支持](https://bitcoinops.org/en/newsletters/2023/09/27/#lnd-7994)
* [LND #7904 为基于 MuSig2 的 taproot 通道增加了实验性支持](https://bitcoinops.org/en/newsletters/2023/08/30/#lnd-7904)
* [现场报告：BitGo 的 Brandon Black 实现 MuSig2](https://bitcoinops.org/en/bitgo-musig2/)
* [针对状态链的盲目 MuSig2 签名的讨论](https://bitcoinops.org/en/newsletters/2023/08/02/#safety-of-blind-musig2-signing)
* [Taproot 和 MuSig2 的 LN 通道](https://bitcoinops.org/en/newsletters/2023/07/26/#taproot-and-musig2-channels)
* [Munstr 钱包使用 nostr 协议进行 MuSig2 通信](https://bitcoinops.org/en/newsletters/2023/05/24/#musig-wallet-munstr-released)
* [Lightning Lab 的 Loop 现在默认使用 MuSig2 以降低费用和提高隐私](https://bitcoinops.org/en/newsletters/2023/05/24/#lightning-loop-defaults-to-musig2)
* [BIPs #1372 将 BIP327 分配给用于创建多重签名的 MuSig2 协议](https://bitcoinops.org/en/newsletters/2023/04/12/#bips-1372)
* [LND #7171 升级了 signrpc RPC 以支持最新的 MuSig2 草案 BIP](https://bitcoinops.org/en/newsletters/2023/02/15/#lnd-7171)

**2022**

* [2022 年回顾：MuSig2](https://bitcoinops.org/en/newsletters/2022/12/21/#musig2)
* [MuSig2 的安全漏洞披露，如草案 BIP 中所述](https://bitcoinops.org/en/newsletters/2022/10/19/#musig2-security-vulnerability)
* [关于设计 LN 升级以支持递归 MuSig2 的讨论](https://bitcoinops.org/en/newsletters/2022/06/15/#recursive-musig2)
* [MuSig2 实现注释](https://bitcoinops.org/en/newsletters/2022/05/04/#musig2-implementation-notes)
* [LND #6361 增加了对 MuSig2 签名的支持](https://bitcoinops.org/en/newsletters/2022/05/04/#lnd-6361)
* [MuSig2 的提议 BIP](https://bitcoinops.org/en/newsletters/2022/04/13/#musig2-proposed-bip)
* [提议在 LN 八卦协议中使用 MuSig2](https://bitcoinops.org/en/newsletters/2022/03/30/#minor-update)

**2021**

* [LN 开发者会议总结，包括 MuSig2 的讨论](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [MuSig1、MuSig2 和 MuSig-DN 的概述](https://bitcoinops.org/en/newsletters/2021/08/04/#using-multisignatures)
* [基准：1 百万签名者与 MuSig](https://bitcoinops.org/en/newsletters/2021/06/30/#possible-amount-of-signatures-with-musig)

**2020**

* [2020 年回顾：MuSig2](https://bitcoinops.org/en/newsletters/2020/12/23/#musig2)
* [MuSig2 论文发布](https://bitcoinops.org/en/newsletters/2020/10/21/#musig2-paper-published)
* [关于 musig 风格多方签名的演示和讨论](https://bitcoinops.org/en/newsletters/2020/07/01/#schnorr-signatures-and-multisignatures)

**2019**

* [Composable MuSig—关于安全使用签名者子群体的担忧](https://bitcoinops.org/en/newsletters/2019/12/04/#composable-musig)
* [MuSig 和基于 Wagner 算法的攻击](https://bitcoinops.org/en/newsletters/2019/11/27/#schnorr-taproot-updates)
* [Schnorr 签名和 musig](https://bitcoinops.org/en/schorr-taproot-workshop/#12-musig)
* [LN 八卦更新提案使用 MuSig](https://bitcoinops.org/en/newsletters/2019/07/17/#gossip-update-proposal)
* [Breaking Bitcoin 演讲：在 bip-taproot 上的安全协议](https://bitcoinops.org/en/newsletters/2019/06/19/#secure-protocols-on-bip-taproot)
* [Optech 行政简报：下一个软分叉](https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork)
* [扩展 PSBT 以使其兼容高级协议的帮助](https://bitcoinops.org/en/newsletters/2019/03/12/#extension-fields-to-partially-signed-bitcoin-transactions-psbts)
* [Libsecp256k1-zkp 支持 MuSig 密钥和签名聚合](https://bitcoinops.org/en/newsletters/2019/02/26/#schnorr-ready-fork-of-libsecp256k1-available)

**2018**

* [2018 年回顾：MuSig 协议的发布](https://bitcoinops.org/en/newsletters/2018/12/28/#january)
* [基于 MuSig 构造的 BLS 签名](https://bitcoinops.org/en/newsletters/2018/08/07/#library-announced-for-bls-signatures)

## 参见

* [无脚本多签名](https://bitcoinops.org/en/topics/multisignature/)
* [Schnorr 签名](https://bitcoinops.org/en/topics/schnorr-signatures/)
