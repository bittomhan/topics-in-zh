# Tapscript

**Tapscript** 是用于 Taproot 脚本路径花费的脚本语言。

它与传统和隔离见证 (Segwit) 比特币脚本共享大多数操作，但有一些不同之处：

* `OP_CHECKMULTISIG` 和 `OP_CHECKMULTISIGVERIFY` 被 `OP_CHECKSIGADD` 操作码取代。
* 许多以前被禁用的操作码被重新定义为 `OP_SUCCESS` 操作码，它们无条件地使整个脚本有效，以简化软分叉升级。
* 与传统脚本或 BIP143 v0 隔离见证不同，签名哈希的计算方式不同。

## 主要代码和文档

* [bip-tapscript](https://github.com/bitcoin/bips/blob/master/bip-0342.mediawiki)

## Optech 新闻简报和网站提及

**2023**

* [研究显示 OP\_SUCCESSx 对使用输出脚本内省的契约的影响](https://bitcoinops.org/en/newsletters/2023/10/25/#op-success-changes-would-be-beneficial)
* [Tapscript 签名可塑性的描述和对 SIGHASH\_ANYPREVOUT 的建议修复](https://bitcoinops.org/en/newsletters/2023/02/15/#tapscript-signature-malleability)

**2022**

* [关于降低 Tapscript 资源限制的讨论](https://bitcoinops.org/en/newsletters/2022/10/19/#block-parsing-bug-affecting-btcd-and-lnd)
* [问题：为什么无效的 `OP_CHECKSIGADD` 签名会使脚本失败？](https://bitcoinops.org/en/newsletters/2022/07/27/#why-do-invalid-signatures-in-op-checksigadd-not-push-to-the-stack)

**2021**

* [Rust Bitcoin #644 为 Tapscript 的新操作码增加支持](https://bitcoinops.org/en/newsletters/2021/10/06/#rust-bitcoin-644)
* [Bitcoin Core #21365 允许钱包为 Tapscript 花费创建签名](https://bitcoinops.org/en/newsletters/2021/06/23/#bitcoin-core-21365)
* [使用备用 Tapscript 花费路径从加密破解中恢复](https://bitcoinops.org/en/newsletters/2021/03/24/#taproot-improvement-in-post-qc-recovery-at-no-onchain-cost)

**2020**

* [2020 年度回顾：Taproot、Tapscript 和 Schnorr 签名](https://bitcoinops.org/en/newsletters/2020/12/23/#taproot)
* [Bitcoin Core #19953 合并了 BIP342 的共识实现](https://bitcoinops.org/en/newsletters/2020/10/21/#bitcoin-core-19953)
* [Bitcoin Core #16902 修复了 OP\_IF 相关操作码的低效问题](https://bitcoinops.org/en/newsletters/2020/03/18/#bitcoin-core-16902)
* [btcdeb 增加了 `tap` 命令用于尝试 Taproot 和 Tapscript](https://bitcoinops.org/en/newsletters/2020/02/05/#taproot-and-tapscript-experimentation-tool)

**2019**

* [2019 年度回顾：Taproot 和 Tapscript](https://bitcoinops.org/en/newsletters/2019/12/28/#taproot)
* [关于使用签名检查操作码的位置承诺的讨论](https://bitcoinops.org/en/newsletters/2019/12/04/#continued-schnorr-taproot-discussion)
* [**Bitcoin Optech Schnorr/Taproot 工作坊**](https://bitcoinops.org/en/schorr-taproot-workshop/)
* [关于 Taproot 的结构化审查公告（包括 Tapscript）](https://bitcoinops.org/en/newsletters/2019/10/23/#taproot-review)
* [关于 Schnorr、Taproot 和 Tapscript 的变化更新](https://bitcoinops.org/en/newsletters/2019/10/16/#taproot-update)
* [Tapscript 资源限制](https://bitcoinops.org/en/newsletters/2019/09/25/#tapscript-resource-limits)
* [BIP322 signmessage 的前向兼容性](https://bitcoinops.org/en/bech32-sending-support/#message-signing-support)
* [行政简报：Taproot 和 Tapscript](https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork)
* [Taproot 和 Tapscript 概述](https://bitcoinops.org/en/newsletters/2019/05/14/#soft-fork-discussion)
* [**BIP-taproot 和 BIP-tapscript 的扩展总结**](https://bitcoinops.org/en/newsletters/2019/05/14/#overview-of-the-taproot--tapscript-proposed-bips)

## 参见

* [Taproot](https://bitcoinops.org/en/topics/taproot/)
