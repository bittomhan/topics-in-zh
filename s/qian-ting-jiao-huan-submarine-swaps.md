# 潜艇交换 - Submarine swaps

**潜艇交换**是一种信任最小化的原子交换，用于将链下比特币和链上比特币进行互换。通过 HTLC（哈希时间锁定合约）保护的支付通过闪电网络路由到服务提供商，服务提供商创建一个链上输出，支付相同的 HTLC。链上接收方可以解决 HTLC 来索取其资金，从而允许闪电网络上的 HTLC 像正常情况下一样被结算。

_这个主题描述是一个存根。我们欢迎通过_ [_pull request_](https://github.com/bitcoinops/bitcoinops.github.io/edit/master/\_topics/en/submarine-swaps.md) _提供更多关于这个主题的背景信息。_

## Optech 新闻简报和网站提及

**2023**

* [提案扩展 BOLT11 发票以请求潜艇交换的预付款](https://bitcoinops.org/en/newsletters/2023/06/21/#submarine-swaps)

**2020**

* [Electrum 4.0.1 增加了对潜艇交换的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#electrum-adds-lightning-network-and-psbt-support)

**2019**

* [Lightning Loop 增加了对用户交换输入的支持](https://bitcoinops.org/en/newsletters/2019/07/03/#lightning-loop-supports-user-loop-ins)
* [Lightning Labs 宣布了一种新工具和服务来促进潜艇交换](https://bitcoinops.org/en/newsletters/2019/03/26/#loop-announced)

## 另见

* [拼接 (Splicing)](https://bitcoinops.org/en/topics/splicing/)
