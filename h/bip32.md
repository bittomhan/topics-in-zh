---
description: 同时涵盖 BIP32 和 HD 钱包（HD wallets）
---

# HD 密钥生成 - HD key generation

**HD 密钥生成** 如 **BIP32** 所指定的，允许从小至 128 位的种子安全地创建无限数量的密钥对。钱包还可以创建扩展公钥（xpubs），使外部软件能够为钱包创建新的公钥，而无需了解相应的私钥。

_此主题描述是一个存根。我们欢迎提供更多关于该主题背景信息的_ [_拉取请求_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/hd-key-generation.md)_。_

## 主要代码和文档

* [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki)

## Optech 新闻简报及网站提及

**2023 年**

* [ColdCard 6.0.0X 添加了对 BIP129 在多签钱包设置过程中交换 xpubs 的支持](https://bitcoinops.org/en/newsletters/2023/05/24/#edge-firmware-for-coldcard-announced)
* [更快的离线验证 BIP32 主种子备份](https://bitcoinops.org/en/newsletters/2023/03/01/#faster-seed-backup-checksums)

**2022 年**

* [提议允许在描述符中使用多个 BIP32 派生路径](https://bitcoinops.org/en/newsletters/2022/08/03/#multiple-derivation-path-descriptors)

**2021 年**

* [HD 钱包恢复中零 HTLC 费用锚定输出协议的复杂性](https://bitcoinops.org/en/newsletters/2021/09/29/#challenges-recovering-ln-close-transactions-using-only-a-seed)
* [实现 Taproot 接收支持不需要更改 BIP32 派生](https://bitcoinops.org/en/newsletters/2021/07/14/#preparing-for-taproot-4-from-p2wpkh-to-single-sig-p2tr)
* [提出用于单签 P2TR 的 BIP32 密钥派生路径](https://bitcoinops.org/en/newsletters/2021/06/30/#key-derivation-path-for-single-sig-p2tr)
* [比特币核心 #22095 添加测试以确保正确填充 BIP32 派生的密钥](https://bitcoinops.org/en/newsletters/2021/06/09/#bitcoin-core-22095)
* [BIPs #1097 为多签钱包设置过程中交换 xpubs 的提案分配了 BIP129](https://bitcoinops.org/en/newsletters/2021/05/26/#bips-1097)
* [BIPs #1089 为多签钱包的标准化 BIP32 路径的提案分配了 BIP87](https://bitcoinops.org/en/newsletters/2021/05/26/#bips-1089)
* [仅使用 BIP32 种子关闭丢失的 LN 通道](https://bitcoinops.org/en/newsletters/2021/05/05/#closing-lost-channels-with-only-a-bip32-seed)
* [关于在多签钱包设置过程中安全交换 BIP32 xpubs 的提案](https://bitcoinops.org/en/newsletters/2021/02/17/#securely-setting-up-multisig-wallets)

**2020 年**

* [为 BIP32 路径模板提出的 BIP](https://bitcoinops.org/en/newsletters/2020/07/08/#proposed-bip-for-bip32-path-templates)
* [BIPs #910 为 BIP32 密钥链中确定性熵的提案分配了 BIP85](https://bitcoinops.org/en/newsletters/2020/06/17/#bips-910)
* [使用一个 BIP32 密钥链为多个子密钥链种子的提案](https://bitcoinops.org/en/newsletters/2020/04/15/#proposal-for-using-one-bip32-keychain-to-seed-multiple-child-keychains)
* [问题：为什么 BIP32 指纹被用于 BIP174 PSBT？](https://bitcoinops.org/en/newsletters/2020/01/29/#why-was-the-bip32-fingerprint-used-for-bip174-psbt)

**2019 年**

* [问题：BIP32 派生路径的最大允许深度是多少？](https://bitcoinops.org/en/newsletters/2019/12/18/#what-is-the-max-allowed-depth-for-bip32-derivation-paths)
* [关于 BIP32 扩展公钥（xpubs）与 ypubs 和 zpubs 的问题](https://bitcoinops.org/en/newsletters/2019/07/31/#why-does-the-importmulti-rpc-not-support-zpub-and-ypub)
* [BIPs #784 更新了 BIP174 PSBT 以包含 BIP32 xpub](https://bitcoinops.org/en/newsletters/2019/07/17/#bips-784)
* [建议在 BIP174 PSBT 中包含 BIP32 派生路径](https://bitcoinops.org/en/newsletters/2019/05/14/#addition-of-derivation-paths-to-bip174-psbts)

**2018 年**

* [比特币核心 #14150 为描述符添加了密钥来源支持，用于跟踪 BIP32 xpubs](https://bitcoinops.org/en/newsletters/2018/10/30/#bitcoin-core-14150)

## 参见

* [输出脚本描述符](https://bitcoinops.org/en/topics/output-script-descriptors/)
