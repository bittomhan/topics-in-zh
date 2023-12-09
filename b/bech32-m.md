---
description: 也涵盖 Bech32、Bech32m、BIP173 和原生隔离见证地址（Native Segwit Address）
---

# Bech32(m)

**Bech32** 和 **Bech32m** 是用于支付原生隔离见证（segwit）输出的地址格式。

Bech32 地址格式只使用 32 个字母和数字，不使用大小写混合，并包括一个错误纠正代码，可以捕获几乎所有地址输入错误（甚至在某些情况下识别错误发生的位置）。地址编码了一个 segwit 版本，使它们与大范围的潜在升级向前兼容。

在发现 bech32 错误检测对未来升级在一些罕见情况下存在 [问题](https://bitcoinops.org/en/newsletters/2019/11/13/#taproot-review-discussion-and-related-information) 后，提出了一种新的修改后的 bech32（**bech32m**）格式。预计 bech32m 将用于 [taproot](https://bitcoinops.org/en/topics/taproot/) 和未来基于 segwit 的脚本升级，要求实现了对原始 bech32 地址格式支付支持的钱包和服务进行升级，如果他们想支持支付 taproot 地址和未来的升级。继续支付原始的（版本 0）segwit 地址的 P2WPKH 和 P2WSH 脚本不需要升级。

## 主要代码和文档

* [BIP173: bech32](https://github.com/bitcoin/bips/blob/master/bip-0173.mediawiki)
* [BIP350: bech32m](https://github.com/bitcoin/bips/blob/master/bip-0350.mediawiki)
* [Bech32(m) 参考代码](https://github.com/sipa/bech32)

## Optech 新闻简报和网站提及

**2022**

* [Bitcoin Core GUI #459 允许用户选择创建 bech32m 地址](https://bitcoinops.org/en/newsletters/2022/01/05/#bitcoin-core-gui-459)

**2021**

* [2021 年度回顾：bech32m 地址](https://bitcoinops.org/en/newsletters/2021/12/22/#bech32m)
* [Bitcoin Core #16807 返回 bech32/bech32m 地址中的输入错误位置](https://bitcoinops.org/en/newsletters/2021/12/01/#bitcoin-core-16807)
* [Rust Bitcoin #691 增加了为 P2TR scriptPubKey 创建 bech32m 地址的 API](https://bitcoinops.org/en/newsletters/2021/11/17/#rust-bitcoin-691)
* [在比特币核心中创建 bech32m 地址的说明](https://bitcoinops.org/en/newsletters/2021/10/20/#testing-taproot)
* [Rust Bitcoin #563 为 P2TR 输出增加了对 bech32m 地址的支持](https://bitcoinops.org/en/newsletters/2021/10/06/#rust-bitcoin-563)
* [Sparrow 钱包增加了对 bech32m 地址的支持](https://bitcoinops.org/en/newsletters/2021/07/21/#sparrow-1-4-3-supports-p2tr)
* [跟踪钱包和服务对 bech32m 支持的 Wiki 页面](https://bitcoinops.org/en/newsletters/2021/07/14/#tracking-bech32m-support)
* [Rust Bitcoin #601 增加了解析 bech32m 地址的支持](https://bitcoinops.org/en/newsletters/2021/06/23/#rust-bitcoin-601)
* [为 Taproot 准备 #1：bech32m 发送支持](https://bitcoinops.org/en/newsletters/2021/06/23/#preparing-for-taproot-1-bech32m-sending-support)- [C-Lightning](https://bitcoinops.org/en/newsletters/2021/06/16/#c-lightning-4591)
* [Electrum 4.1.0 增加了对 bech32m 的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#electrum-4-1-0-enhances-lightning-features)
* [Blockchain.com 增加了对 bech32 接收和支付的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#blockchain-com-supports-segwit)
* [Bitcoin Core #20861 实现了对 bech32m 地址的支持](https://bitcoinops.org/en/newsletters/2021/03/24/#bitcoin-core-20861)
* [BitMEX 交易所宣布支持 bech32 存款地址](https://bitcoinops.org/en/newsletters/2021/03/24/#bitmex-announces-bech32-support)
* [BTCPay Server #2181 在二维码中将 bech32 地址大写](https://bitcoinops.org/en/newsletters/2021/03/10/#btcpay-server-2181)
* [BIPs #1056 增加了 BIP350 以支持 bech32m](https://bitcoinops.org/en/newsletters/2021/02/10/#bips-1056)
* [bech32m 的草案 BIP](https://bitcoinops.org/en/newsletters/2021/01/13/#bech32m)

**2020**

* [2020 年度回顾：Taproot 对修改后的 bech32 地址格式的需求](https://bitcoinops.org/en/newsletters/2020/12/23/#taproot)
* [问答：‘原生 Segwit’和‘Bech32’之间有什么区别？](https://bitcoinops.org/en/newsletters/2020/12/16/#what-is-the-difference-between-native-segwit-and-bech32)
* [大写架构的 QR 编码 Bech32 BIP21 发票问题](https://bitcoinops.org/en/newsletters/2020/12/09/#thwarted-upgrade-to-uppercase-bech32-qr-codes)
* [Bech32 算法修订研究和提案](https://bitcoinops.org/en/newsletters/2020/12/09/#bech32-addresses-for-taproot-and-beyond)
* [关于更新 BIP173 Bech32 以解决可变性问题的讨论](https://bitcoinops.org/en/newsletters/2020/10/14/#bech32-addresses-for-taproot)
* [提议更新 BIP173 Bech32 以解决可变性问题](https://bitcoinops.org/en/newsletters/2020/07/22/#bech32-address-updates)

**2019**

* [2019 年度回顾：Bech32 的可变性](https://bitcoinops.org/en/newsletters/2019/12/28/#bech32-mutability)
* [提出的计划应对变长地址中的 Bech32 可篡改性](https://bitcoinops.org/en/newsletters/2019/12/18/#review-bech32-action-plan)
* [Bech32 错误检测能力的分析](https://bitcoinops.org/en/newsletters/2019/12/18/#analysis-of-bech32-error-detection)
* [LND #3767 拒绝了带有有效 Bech32 校验和的格式错误的 BOLT11 发票](https://bitcoinops.org/en/newsletters/2019/12/11/#lnd-3767)
* [Bech32 长度扩展变异弱点是如何工作的？](https://bitcoinops.org/en/newsletters/2019/11/27/#how-does-the-bech32-length-extension-mutation-weakness-work)
* [Bech32 长度变更可变性对 v1 segwit 脚本长度的影响](https://bitcoinops.org/en/newsletters/2019/11/13/#taproot-review-discussion-and-related-information)
* [**Bech32 发送支持（24 部分系列）**](https://bitcoinops.org/en/bech32-sending-support/)

**2018**

* [C 语言实现的 Bech32 安全更新](https://bitcoinops.org/en/newsletters/2018/11/06#bech32-security-update-for-c-implementation)

## 参见

* [Javascript Bech32 演示解码器](http://bitcoin.sipa.be/bech32/demo/demo.html)
