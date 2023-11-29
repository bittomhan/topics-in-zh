---
description: 同时涵盖 二方ECDSA（2pECDSA）和双方ECDSA（Two-Party ECDSA）
---

# 无脚本多重签名（Scriptless Multisignatures）

**无脚本多重签名** 是使用两个或多个私钥创建的数字签名，可以仅使用单个公钥和单个签名进行验证。

无脚本多重签名可以与_有脚本的多签名（scripted multisig）_ 进行比较，后者使用比特币的 `OP_CHECKMULTISIG` 和 `OP_CHECKMULTISIGVERIFY` 操作码（以及为 [tapscript](https://bitcoinops.org/en/topics/tapscript/) 提议的 `OP_CHECKSIGADD` 操作码）来使用公钥和签名。多重签名的优势在于，当它们用于比特币交易时，只有单个密钥和单个签名会在链上公布，允许无限数量的签名者支付与单个签名者为同一交易支付的相同交易费用。多重签名支付与单签名支付无法区分，还为两种支付的创建者提供了更大的隐私。

尽管所有版本的比特币都支持 ECDSA 算法的多重签名创建，但为 [施诺尔签名（schnorr signatures）](https://bitcoinops.org/en/topics/schnorr-signatures/) 创建多重签名更容易，并且已知有几种算法，其中 [MuSig](https://bitcoinops.org/en/topics/musig/) 是专门为比特币用户的需求而创建的。

**术语**：下表总结了_多重签名_和相关术语之间的区别。

<table><thead><tr><th width="161">术语</th><th width="98">私钥数量</th><th width="210">消息数量（例如：交易输入）</th><th width="146">公开的公钥数量</th><th>签名数量</th><th>需要的签名者数量</th><th>备注</th></tr></thead><tbody><tr><td>有脚本的多签名（Scripted Multisig）</td><td>m</td><td>1</td><td>m</td><td>k 其中 k&#x3C;=m</td><td>k</td><td>使用比特币脚本多签名操作码</td></tr><tr><td><a href="https://bitcoinops.org/en/topics/multisignature/">无脚本多重签名</a></td><td>m</td><td>1</td><td>1</td><td>1</td><td>m</td><td>与单签名在链上无法区分</td></tr><tr><td><a href="https://bitcoinops.org/en/topics/threshold-signature/">门限签名（Threshold Signature）</a></td><td>m</td><td>1</td><td>1</td><td>1</td><td>k 其中 k&#x3C;=m</td><td>与单签名在链上无法区分</td></tr></tbody></table>

## Optech 新闻稿和网站提及

**2023年**

* [当与多重签名一起使用时，对签名适配器安全性的分析](https://bitcoinops.org/en/newsletters/2023/05/03/#analysis-of-signature-adaptor-security)
* [BIPs #1372 将 BIP327 分配给用于创建多重签名的 MuSig2 协议](https://bitcoinops.org/en/newsletters/2023/04/12/#bips-1372)

**2022年**

* [关于不同脚本类型可能的最大多签名群的问题](https://bitcoinops.org/en/newsletters/2022/06/29/#what-is-the-largest-multisig-quorum-currently-possible)

**2021年**

* [为 taproot 准备：多重签名随机数的挑战](https://bitcoinops.org/en/newsletters/2021/08/11/#preparing-for-taproot-8-multisignature-nonces)
* [为 taproot 准备：多重签名概述](https://bitcoinops.org/en/newsletters/2021/08/04/#preparing-for-taproot-7-multisignatures)
* [无需多重签名支持的签名适配器](https://bitcoinops.org/en/newsletters/2021/04/28/#support-for-ecdsa-signature-adaptors-added-to-libsecp256k1-zkp)

**2020年**

* [关于多重签名和门限签名的讨论](https://bitcoinops.org/en/newsletters/2020/07/01/#schnorr-signatures-and-multisignatures)
* [关于使用 160 位地址进行简单多方多重签名的警告](https://bitcoinops.org/en/newsletters/2020/06/24/#reminder-about-collision-attack-risks-on-two-party-ecdsa)
* [签名适配器的 ECDSA 多重签名替代方案](https://bitcoinops.org/en/newsletters/2020/04/08/#work-on-ptlcs-for-ln-using-simplified-ecdsa-adaptor-signatures)
* [减轻功率分析攻击的方法，包括针对多重签名方案的攻击](https://bitcoinops.org/en/newsletters/2020/04/01/#mitigating-differential-power-analysis-in-schnorr-signatures)
* [使用多重签名实现 ECDSA 的状态链](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)
* [BIPs #876 将 BIP340 分配给新的兼容多重签名方案](https://bitcoinops.org/en/newsletters/2020/01/29/#bip340)

**2019年**

* [关于嵌套和可组合多重签名方案的讨论](https://bitcoinops.org/en/newsletters/2019/12/04/#continued-schnorr-taproot-discussion)
* [关于减少交互需求的施诺尔多重签名方案的工作](https://bitcoinops.org/en/newsletters/2019/11/27/#schnorr-taproot-updates)
* [关于 taproot 如何在与多重签名结合使用时提高扩展性的讨论](https://bitcoinops.org/en/newsletters/2019/09/18/#blockchain-design-patterns-layers-and-scaling-approaches)

**2018年**

* [发表了关于快速 ECDSA 多重签名的两篇论文](https://bitcoinops.org/en/newsletters/2018/10/23/#two-papers-published-on-fast-multiparty-ecdsa)
* [无脚本闪电网络支付通道的 ECDSA 多重签名](https://bitcoinops.org/en/newsletters/2018/10/09/#multiparty-ecdsa-for-scriptless-lightning-network-payment-channels)

## 参见

* [MuSig](https://bitcoinops.org/en/topics/musig/)
* [签名适配器（Signature Adaptors）](https://bitcoinops.org/en/topics/adaptor-signatures/)
* [门限签名（Threshold Signature）](https://bitcoinops.org/en/topics/threshold-signature/)
