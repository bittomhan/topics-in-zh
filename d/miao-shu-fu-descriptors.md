---
description: 也涵盖输出脚本描述符（Output script descriptors）
---

# 描述符 - Descriptors

**输出脚本描述符**是包含所有必要信息的字符串，使钱包或其他程序能够追踪支付给特定脚本或一组相关脚本（即一个地址或一组相关地址，如在 HD 钱包中）的款项。

描述符与 [miniscript](https://bitcoinops.org/en/topics/miniscript/) 结合使用，使钱包能够处理和签名更多种类的脚本。它们也与 [PSBTs](https://bitcoinops.org/en/topics/psbt/)（Partially Signed Bitcoin Transactions，部分签名比特币交易）结合得很好，使钱包能够确定它在多重签名脚本中控制哪些密钥。

## 主要代码和文档

* [输出脚本描述符](https://github.com/bitcoin/bitcoin/blob/master/doc/descriptors.md)

## Optech 新闻简报和网站提及

**2023**

* [比特币核心 #27255 将 miniscript 移植到 tapscript，提供 tapscript 描述符](https://bitcoinops.org/en/newsletters/2023/10/18/#bitcoin-core-27255)
* [BIPs #1354 添加 BIP389，用于多个衍生路径描述符](https://bitcoinops.org/en/newsletters/2023/07/05/#bips-1354)
* [比特币核心 #24149 添加了对基于 P2WSH 的 miniscript 输出描述符的签名支持](https://bitcoinops.org/en/newsletters/2023/02/22/#bitcoin-core-24149)

**2022**

* [2022 年回顾：比特币核心中的 miniscript 描述符](https://bitcoinops.org/en/newsletters/2022/12/21/#miniscript-descriptors)
* [部分描述符如何帮助创建 tapleaf 树](https://bitcoinops.org/en/newsletters/2022/08/31/#why-isn-t-it-possible-to-add-an-op-return-commitment-or-some-arbitrary-script-inside-a-taproot-script-path-with-a-descriptor)
* [提出了用于静默支付的新描述符](https://bitcoinops.org/en/newsletters/2022/08/24/#updated-silent-payments-pr)
* [比特币核心 #23480 添加了 `rawtr()` 描述符](https://bitcoinops.org/en/newsletters/2022/08/17/#bitcoin-core-23480)
* [提出 BIP 以在描述符中允许多个衍生路径](https://bitcoinops.org/en/newsletters/2022/08/03/#multiple-derivation-path-descriptors)
* [比特币核心 #24148 为包含 miniscript 的描述符添加了仅监视支持](https://bitcoinops.org/en/newsletters/2022/07/20/#bitcoin-core-24148)
* [关于描述符支持 miniscript 的 PR 审查俱乐部](https://bitcoinops.org/en/newsletters/2022/06/08/#bitcoin-core-pr-review-club)
* [为硬件签名设备调整描述符和 miniscript](https://bitcoinops.org/en/newsletters/2022/05/18/#adapting-miniscript-and-output-script-descriptors-for-hardware-signing-devices)
* [比特币核心 #24043 添加了新的 `multi_a` 和 `sortedmulti_a` 描述符，用于 taproot 多重签名](https://bitcoinops.org/en/newsletters/2022/03/16/#bitcoin-core-24043)
* [HWI #545 为 taproot`tr()` 描述符添加支持](https://bitcoinops.org/en/newsletters/2022/01/05/#hwi-545)

**2021**

* [2021 年回顾：输出脚本描述符（output script descriptors）](https://bitcoinops.org/en/newsletters/2021/12/22/#descriptors)
* [比特币核心（Bitcoin Core）#22364 添加了在钱包中创建塔普根描述符（taproot descriptors）的支持](https://bitcoinops.org/en/newsletters/2021/12/01/#bitcoin-core-22364)
* [比特币核心 #23002 使基于描述符的钱包成为新钱包的默认设置](https://bitcoinops.org/en/newsletters/2021/10/27/#bitcoin-core-23002)
* [Coldcard 4.1.3 添加了对基于描述符钱包（descriptor-based wallets）的支持](https://bitcoinops.org/en/newsletters/2021/10/20/#coldcard-supports-descriptor-based-wallets)
* [BIPs #1143 引入了 BIPs 380-386，专门描述输出脚本描述符](https://bitcoinops.org/en/newsletters/2021/09/08/#bips-1143)
* [输出脚本描述符与有版本和无版本的 BIP32 种子（BIP32 seeds）的对比](https://bitcoinops.org/en/newsletters/2021/07/14/#fn:electrum-segwit)
* [七个 BIP 提案，用于标准化输出脚本描述符](https://bitcoinops.org/en/newsletters/2021/07/07/#bips-for-output-script-descriptors)
* [为塔普根（taproot）做准备：输出脚本描述符](https://bitcoinops.org/en/newsletters/2021/07/07/#preparing-for-taproot-3-taproot-descriptors)
* [比特币核心 #19651 添加了通过 `importdescriptor` 更新描述符的支持](https://bitcoinops.org/en/newsletters/2021/07/07/#bitcoin-core-19651)
* [比特币核心 #22051 添加了为塔普根输出（taproot outputs）导入描述符的支持](https://bitcoinops.org/en/newsletters/2021/06/09/#bitcoin-core-22051)
* [BIPs #1089 分配了 BIP87 给一个使用描述符的多重签名钱包标准](https://bitcoinops.org/en/newsletters/2021/05/26/#bips-1089)
* [比特币核心 #20867 将描述符的最大多重签名密钥增加到 20 个](https://bitcoinops.org/en/newsletters/2021/05/12/#bitcoin-core-20867)
* [Specter-DIY v1.5.0 添加了完整的描述符支持](https://bitcoinops.org/en/newsletters/2021/04/21/#specter-diy-v1-5-0)
* [Specter v1.2.0 包括对比特币核心描述符钱包（Bitcoin Core descriptor wallets）的支持](https://bitcoinops.org/en/newsletters/2021/03/24/#specter-v1-2-0-released)
* [比特币核心 #19136 扩展了 `getaddressinfo` 以返回父描述符](https://bitcoinops.org/en/newsletters/2021/02/24/#bitcoin-core-19136)
* [比特币开发套件（Bitcoin Dev Kit）v0.2.0 发布，支持描述符](https://bitcoinops.org/en/newsletters/2021/02/17/#bitcoin-dev-kit-v0-3-0-released)
* [比特币核心 #20226 为其钱包添加了新的 `listdescriptors` RPC](https://bitcoinops.org/en/newsletters/2021/02/03/#bitcoin-core-20226)
* [比特币核心 0.21.0 发布，包含实验性的本地描述符钱包（native descriptor wallets）](https://bitcoinops.org/en/newsletters/2021/01/20/#bitcoin-core-0-21-0)
* [BTCPay Server 1.0.6.7 发布，支持在钱包设置中使用描述符](https://bitcoinops.org/en/newsletters/2021/01/20/#btcpay-server-1-0-6-7)
* [BTCPay Server #2169 添加了导入某些描述符的功能](https://bitcoinops.org/en/newsletters/2021/01/20/#btcpay-server-2169)

**2020**

* [比特币钱包跟踪器（Bitcoin Wallet Tracker, BWT）添加了对描述符的支持](https://bitcoinops.org/en/newsletters/2020/12/16/#bitcoin-wallet-tracker-adds-descriptor-support)
* [关于从传统钱包迁移到描述符钱包的问答](https://bitcoinops.org/en/newsletters/2020/11/25/#how-will-the-migration-tool-from-a-bitcoin-core-legacy-wallet-to-a-descriptor-wallet-work)
* [C-Lightning #4171 允许检索钱包的链上描述符（onchain descriptors）](https://bitcoinops.org/en/newsletters/2020/11/18/#c-lightning-4171)
* [现场报告：River Financial 使用描述符](https://bitcoinops.org/en/river-descriptors-psbt/)
* [比特币核心 #16528 添加了对本地输出描述符钱包（native output descriptor wallets）的支持](https://bitcoinops.org/en/newsletters/2020/05/06/#bitcoin-core-16528)
* [比特币核心 #18032 在多重签名地址 RPC 中添加了 `descriptor` 字段](https://bitcoinops.org/en/newsletters/2020/02/12/#bitcoin-core-18032)
* [编码描述符（例如，使用 base64）](https://bitcoinops.org/en/newsletters/2020/01/08/#encoded-descriptors)

**2019**

* [描述符扩展包括 sortedmulti](https://bitcoinops.org/en/newsletters/2019/10/16/#bitcoin-core-17056)
* [添加了描述符校验和支持](https://bitcoinops.org/en/newsletters/2019/02/19/#bitcoin-core-15368)

**2018**

* [支持密钥起源（Key origin support）](https://bitcoinops.org/en/newsletters/2018/10/30/#bitcoin-core-14150)
* [比特币核心首次使用描述符](https://bitcoinops.org/en/newsletters/2018/07/24/#first-use-of-output-script-descriptors)

## 参见

* [Miniscript（小脚本）](https://bitcoinops.org/en/topics/miniscript/)
* [部分签名比特币交易（Partially-Signed Bitcoin Transactions, PSBTs）](https://bitcoinops.org/en/topics/psbt/)
