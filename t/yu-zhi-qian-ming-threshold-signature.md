# 阈值签名 - Threshold signature

**阈值签名**是一种数字签名，可以由之前用于创建相应公钥的私钥的授权子集创建。阈值签名只需使用单一公钥和单一签名即可进行验证。

创建阈值签名有不同的算法，其中最简单的算法之一是对创建[无脚本多重签名](https://bitcoinops.org/en/topics/multisignature/)的典型算法的轻微扩展。这可以通过一个例子来最容易解释：参与者 A、B 和 C 希望接收可以由他们任意三人花费的资金。他们合作创建一个用于接收资金的普通多重签名公钥，然后他们每个人都采取额外的步骤，从他们的私钥派生两个[秘密份额](https://en.wikipedia.org/wiki/Verifiable\_secret\_sharing)——为其他两个参与者中的每一个派生一个份额。这些份额被创建为任意两个份额都可以重构创建它的私钥。每个参与者将不同的秘密份额交给其他参与者，因此每个参与者最终都必须存储他们自己的私钥和为其他每个参与者存储一个份额。然后，每个参与者都能够验证他们收到的份额是否正确派生（即不是伪造的）并且与其他参与者收到的份额不同。

后来，A 和 B 决定在没有 C 的情况下创建一个签名。A 和 B 相互分享他们各自拥有的 C 的两个份额。这使他们能够重构 C 的私钥。A 和 B 也拥有他们自己的私钥，使他们拥有创建多重签名所需的所有三个密钥。

上面的例子只涵盖了最简单的阈值签名算法。还存在其他算法，这些算法减少了概念上的简单性，但提供了额外的功能，例如减少所需的步骤数量或提供对通信问题的增强抵抗力。

## 与多重签名脚本的比较

比特币的 Script 语言（包括提议的 [tapscript](https://bitcoinops.org/en/topics/tapscript/) 修改替代方案）允许为一组 _n_ 个密钥提供阈值 _k_ 个签名，通常称为 k-of-n 多重签名。这需要在任何链上交易中提供 _k_ 个签名和 _n_ 个公钥。

相比之下，阈值签名只需要单一公钥和单一签名，无论涉及多少参与者。这可以显著减少交易的大小，相应地降低交易费用。它还增加了隐私：没有人能够知道哪些方签名（甚至不能知道是否需要多方签名）。

签名者隐私确实为希望第三方可审计哪些方签名的方案带来了问题。审计可以通过独立系统实现（例如，使所有参与者之间的通信通过日志服务器）。有时也可以使用巧妙的构造实现，例如在 [taproot](https://bitcoinops.org/en/topics/taproot/) 的 2-of-3 阈值方案中，常规签名者（A 和 B）可以使用 2-of-2 多重签名的键路径花费，而两种替代方案（A 和 C，或 B 和 C）可以在脚本路径花费的默克尔树中的已知位置拥有他们自己的 2-of-2 多重签名。通过查看花费，参与者可以准确确定哪两方签名。

## 术语

以下表格总结了_阈值签名_与相关术语之间的差异。

| 术语                                                            | 私钥数量 | 消息（例如交易输入） | 公开的公钥 | 签名      | 所需签名者   | 备注                   |
| ------------------------------------------------------------- | ---- | ---------- | ----- | ------- | ------- | -------------------- |
| 脚本化多重签名                                                       | m    | 1          | m     | k（k<=m） | k       | 使用比特币 Script 多重签名操作码 |
| [无脚本多重签名](https://bitcoinops.org/en/topics/multisignature/)   | m    | 1          | 1     | 1       | m       | 在链上与单签不可区分           |
| [阈值签名](https://bitcoinops.org/en/topics/threshold-signature/) | m    | 1          | 1     | 1       | k（k<=m） | 在链上与单签不可区分           |

## Optech 新闻简报和网站提及

**2023**

* [使用 FROST 实现隐私增强的交易共同签名的想法](https://bitcoinops.org/en/newsletters/2023/09/06/#privacy-enhanced-co-signing)
* [FROST 阈值签名方案的实验性实现公告](https://bitcoinops.org/en/newsletters/2023/08/23/#frost-software-frostsnap-announced)

**2022**

* [关于 FROST 和 ROAST 阈值签名方案的演讲记录](https://bitcoinops.org/en/newsletters/2022/10/26/#frost)

**2020**

* [关于数字签名方案的讨论，包括阈值签名](https://bitcoinops.org/en/newsletters/2020/07/01/#schnorr-signatures-and-multisignatures)

**2019**

* [关于实用阈值 Schnorr 签名的追求演讲总结](https://bitcoinops.org/en/newsletters/2019/10/16/#the-quest-for-practical-threshold-schnorr-signatures)
* [关于 BIP-taproot/ 阈值签名与 MuSig 的安全协议演讲总结](https://bitcoinops.org/en/newsletters/2019/06/19/#secure-protocols-on-bip-taproot)
* [关于阈值钱包中的密码学漏洞演讲总结](https://bitcoinops.org/en/newsletters/2019/06/19/#cryptographic-vulnerabilities-in-threshold-wallets)

**2018**

* [关于 ECDSA 阈值签名的论文发表](https://bitcoinops.org/en/newsletters/2018/10/23/#two-papers-published-on-fast-multiparty-ecdsa)
* [基于配对的阈值签名与签名者审计性](https://bitcoinops.org/en/newsletters/2018/10/09/#compact-multi-signatures-for-smaller-blockchains)

## 参见

* [无脚本多重签名](https://bitcoinops.org/en/topics/multisignature/)
