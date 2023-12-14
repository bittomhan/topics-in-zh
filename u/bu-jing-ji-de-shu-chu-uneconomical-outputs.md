---
description: 也涵盖粉尘（Dust）
---

# 不经济的输出 - Uneconomical outputs

**不经济的输出**指的是交易输出的价值低于花费它们将要支付的费用。为了防止用户创建会增加 UTXO 集大小的不经济输出，比特币核心（Bitcoin Core）和其他节点拒绝转发或挖掘输出值低于特定值的交易，这个特定值被称为 **粉尘限制（dust limit）**。

**术语**：有时，粉尘（dust）被用作不经济输出_或更通用的_低价值输出_的同义词。这可能造成混淆，如 [粉尘攻击（dust attacks）](https://bitcoinops.org/en/topics/output-linking/) 的情况，它涉及的金额刚好超过粉尘限制。Optech [建议](https://github.com/bitcoinops/bitcoinops.github.io/blob/master/STYLE.md)使用_不经济输出_来指那些花费成本不值得的输出，并保留粉尘这个术语专门用于提到粉尘限制。

## 主要代码和文档

* [Bitcoin Core 粉尘限制代码注释](https://github.com/bitcoin/bitcoin/blob/439e58c4d8194ca37f70346727d31f52e69592ec/src/policy/policy.cpp#L14)

## Optech 新闻简报和网站提及

**2023**

* [BOLTs #919 建议 LN 节点限制他们对不经济的 HTLCs 的最大暴露](https://bitcoinops.org/en/newsletters/2023/08/23/#bolts-919)

**2022**

* [关于允许交易包中的不经济输出的讨论](https://bitcoinops.org/en/newsletters/2022/10/05/#ephemeral-dust)
* [BDK #689 允许钱包创建违反粉尘限制的交易](https://bitcoinops.org/en/newsletters/2022/09/07/#bdk-689)
* [关于从 UTXO 集中移除不经济输出的问题的讨论](https://bitcoinops.org/en/newsletters/2022/07/27/#does-an-uneconomical-output-need-to-be-kept-in-the-utxo-set)

**2021**

* [关于为特定情况取消粉尘限制的讨论](https://bitcoinops.org/en/newsletters/2021/12/15/#adding-a-special-exception-for-certain-uneconomical-outputs)
* [Bitcoin Core #22863 记录了 P2TR 粉尘金额](https://bitcoinops.org/en/newsletters/2021/10/20/#bitcoin-core-22863)
* [BOLTs #894 规定了与 LN 中不经济支付相关的各种检查](https://bitcoinops.org/en/newsletters/2021/10/20/#bolts-894)
* [多个 LN 实现对不经济支出的 CVE 漏洞易受攻击](https://bitcoinops.org/en/newsletters/2021/10/13/#ln-spend-to-fees-cve)
* [多个实现了 BOLTs #894 的 LN，允许使用更低的承诺交易粉尘限制](https://bitcoinops.org/en/newsletters/2021/10/06/#eclair-1900)
* [Rust-Lightning #1009 添加了 `max_dust_htlc_exposure_msat` 通道配置选项](https://bitcoinops.org/en/newsletters/2021/08/18/#rust-lightning-1009) - [关于取消粉尘限制的讨论](https://bitcoinops.org/en/newsletters/2021/08/18/#dust-limit-discussion)

**2020**

* [LND #3809 在 BumpFee RPC 中添加了一个强制参数，以便它可以花费不经济的 UTXOs](https://bitcoinops.org/en/newsletters/2020/01/29/#lnd-3809)

**2019**

* [问题：粉尘限制是如何确定的？](https://bitcoinops.org/en/newsletters/2019/04/30/#how-was-the-dust-limit-of-546-satoshis-was-chosen-why-not-550-satoshis)
* [问题：LN 如何处理粉尘和不经济支付？](https://bitcoinops.org/en/newsletters/2019/04/30/#do-htlcs-work-for-micropayments)

## 参见

* [粉尘攻击（Dust attacks）](https://bitcoinops.org/en/topics/output-linking/)
* [短暂锚点（Ephemeral anchors）](https://bitcoinops.org/en/topics/ephemeral-anchors/)
