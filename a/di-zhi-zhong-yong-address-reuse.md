---
description: 同时涵盖输出链接（Output Linking）、尘埃攻击（Dust Attacks）和避免重用（Reuse Avoidance）
---

# 地址重用 - Address Reuse

**输出链接（Output Linking）** 也被称为 **地址重用（Address Reuse）** 发生在用户接收到两个或多个支付到同一个公钥或其他独特脚本元素的情况。这可能是因为用户出于无知重用了一个地址，或者是因为蓄意攻击，如在\*\*尘埃攻击（Dust Attack）\*\*中。限制由于输出链接导致的隐私损失的方法归类为 **避免重用（Reuse Avoidance）**。

当您接收到多个支付到同一个比特币地址时，其他用户可以合理地假设同一个人收到了所有这些支付，即使这些支付后来在不同的交易中被花费。为了防止第三方建立此类联系，鼓励用户通过为他们接收的每一笔支付生成一个新地址来执行避免重用。

不幸的是，用户对他们收到的支付没有完全的控制。在尘埃攻击中，攻击者向已经出现在区块链上的地址发送少量比特币，即使是试图避免重用的有良心的用户也会产生地址重用。一些钱包试图通过实施强制性的币选择（coin control）来解决这个问题，帮助用户防止在他们想要保护隐私的交易中花费尘埃。其他钱包提供可选功能，将收到的所有硬币在同一时间花费在同一地址上——但不超过一次——消除了地址重用带来的隐私损失，但风险是可能无法花费收到的资金到之前使用的地址。

地址重用还可能使使用有缺陷软件的用户比没有重用地址的用户更容易受到攻击，例如在软件重用数字签名随机数的情况下。

## 主要代码和文档

* [地址重用（Bitcoin Wiki）](https://en.bitcoin.it/wiki/Address\_reuse)

## Optech 新闻简报和网站提及

**2022 年**

* [唯一地址服务器的建议](https://bitcoinops.org/en/newsletters/2022/10/12/#recommendations-for-unique-address-servers)
* [BIP47 可重用支付代码的更新替代方案](https://bitcoinops.org/en/newsletters/2022/07/06/#updated-alternative-to-bip47-reusable-payment-codes)
* [静默地址的实验](https://bitcoinops.org/en/newsletters/2022/06/01/#experimentation-with-silent-payments)
* [脱链可重用地址的静默地址](https://bitcoinops.org/en/newsletters/2022/04/06/#delinked-reusable-addresses)

**2021 年**

* [为 Taproot 准备：新输出脚本对输出链接的影响](https://bitcoinops.org/en/newsletters/2021/10/06/#preparing-for-taproot-16-output-linking)
* [比特币核心 #23065 允许钱包持久性阻止花费垃圾 UTXO](https://bitcoinops.org/en/newsletters/2021/10/06/#bitcoin-core-23065)
* [重用基于哈希的地址不提供量子抵抗](https://bitcoinops.org/en/newsletters/2021/03/24/#hashes-not-currently-doing-a-good-job-at-qc-resistance)

**2020 年**

* [2020 年度回顾：交易来源隐私](https://bitcoinops.org/en/newsletters/2020/12/23/#transaction-origin-privacy)
* [比特币核心 #17843 修复了与 `avoid_reuse` 标志相关的余额差异](https://bitcoinops.org/en/newsletters/2020/01/22/#bitcoin-core-17843)
* [比特币核心 #17621 修复了 `avoid_reuse` 标志可能导致的潜在隐私泄露](https://bitcoinops.org/en/newsletters/2020/01/15/#bitcoin-core-17621)

**2019 年**

* [比特币核心 0.19 新功能：`avoid_reuse` 钱包标志](https://bitcoinops.org/en/newsletters/2019/11/27/#optional-privacy-preserving-address-management)
* [比特币核心 #13756 添加了 `avoid_reuse` 钱包标志](https://bitcoinops.org/en/newsletters/2019/06/26/#bitcoin-core-13756)
* [Esplora 区块浏览器更新，针对地址重用提出隐私警告](https://bitcoinops.org/en/newsletters/2019/03/19/#esplora-updated)
* [在重用地址中发现的弱签名随机数](https://bitcoinops.org/en/newsletters/2019/01/15/#weak-signature-nonces-discovered)

**2018 年**

* [比特币核心 #12257：新的 `avoidpartialspends` 配置选项](https://bitcoinops.org/en/newsletters/2018/07/31/#bitcoin-core-12257)

## 参见

* [不经济的输出（尘埃）（Uneconomical Outputs (Dust)）](https://bitcoinops.org/en/topics/uneconomical-outputs/)
