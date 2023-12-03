# 拼接 - Splicing

**拼接**是指将资金从链上输出转移到支付通道中，或者从支付通道转移到独立的链上输出，而通道参与者无需等待确认延迟即可使用通道的其他资金。

拼接有两种类型：

* **拼接进 (Splice in)**意味着向通道增加资金。在这种情况下，参与方之间安排了通道的合作关闭，将旧通道资金和新存款一起支付到新通道。由于新通道的开启基于旧通道关闭的安全性，通道参与者在等待关闭和开启交易确认的同时可以安全地在通道内使用旧资金。
* **拼接出 (Splice out)**意味着将资金从通道中取出到独立的链上输出。与拼接进类似，通道关闭并且打开了一个新通道，剩余资金在新通道完全确认前由旧通道的安全性保障。

拼接与[潜艇交换](https://bitcoinops.org/en/topics/submarine-swaps/)（例如 [Lightning Loop](https://blog.lightning.engineering/posts/2019/03/20/loop.html) 实现的那种）不同，在潜艇交换中，资金在用户之间转移以换取链上交易——在潜艇交换中，通道的总余额保持不变；在拼接中，通道的总余额发生变化。

## 主要代码和文档

* [拼接规范（草案）](https://github.com/lightning/bolts/pull/863)
* [Rusty Russell 提出的拼接提议](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-October/001434.html)
* [Rene Pickhardt 提出的拼接提议](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-October/001437.html)

## Optech 新闻简报和网站提及

**2023**

* [Core Lightning #6253 和 #5675 添加了拼接的实验性实现](https://bitcoinops.org/en/newsletters/2023/08/09/#core-lightning-6253)
* [Eclair #2680 为拼接添加了静默协商](https://bitcoinops.org/en/newsletters/2023/08/02/#eclair-2680)
* [Phoenix 钱包增加了拼接支持](https://bitcoinops.org/en/newsletters/2023/07/19/#phoenix-wallet-adds-splicing-support)
* [Eclair #2584 添加了对拼接进和拼接出的支持](https://bitcoinops.org/en/newsletters/2023/04/19/#eclair-2584)
* [关于拼接规范的讨论，包括相对金额和最小化冗余数据](https://bitcoinops.org/en/newsletters/2023/04/12/#splicing-specification-discussions)
* [Eclair #2595 继续该项目对拼接的支持工作](https://bitcoinops.org/en/newsletters/2023/02/22/#eclair-2595)
* [Eclair #2540 为拼接做后端准备](https://bitcoinops.org/en/newsletters/2023/02/01/#eclair-2540)

**2022**

* [BOLTs #1004 提出了支持未来拼接检测的建议](https://bitcoinops.org/en/newsletters/2022/08/24/#bolts-1004)
* [关于最佳方式公布通道拼接的讨论](https://bitcoinops.org/en/newsletters/2022/07/06/#announcing-splices)

**2021**

* [基于交互式资金协议的闪电网络拼接草案规范](https://bitcoinops.org/en/newsletters/2021/04/28/#draft-specification-for-ln-splicing)

**2018**

* [2018 年综述：拼接](https://bitcoinops.org/en/newsletters/2018/12/28/#splicing)
* [闪电网络 1.1 协议目标](https://bitcoinops.org/en/newsletters/2018/11/20/#splicing)
* [闪电网络拼接的提议](https://bitcoinops.org/en/newsletters/2018/10/16/#proposal-for-lightning-network-payment-channel-splicing)

## 参见

* [交互式交易构建协议](https://bitcoinops.org/en/topics/dual-funding/)
* [潜艇交换](https://bitcoinops.org/en/topics/submarine-swaps/)
