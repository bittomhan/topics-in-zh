# 异步支付 - Async Payments

**异步支付（Async Payments）** 是指在接收方离线时进行的闪电网络（LN）支付，这些支付由转发节点（理想情况下是无需信任的方式）保留，并在接收方重新上线时交付。

传统的比特币链上支付是异步的，因为接收方可以生成一个输出脚本（比特币地址）并随时将该地址提供给支付方，然后支付方可以随时支付给该地址——即使接收方离线。保障这笔支付（接收区块确认）的过程不需要接收方采取任何行动。

对于 LN 来说，接收方需要在收到支付时释放一个秘密，以确保支付的安全。这要求支付的发送方和接收方同时在线。在许多情况下，支付方在线并不是一个重大问题，因为他们已经启动了支付过程，并可以触发操作以确保支付被发送。但对于某些接收方来说，在线接收支付更具挑战性。例如，运行在移动电话上的 LN 节点可能有时完全断开互联网连接，并且可能因为节点应用程序在后台运行而无法访问网络。

[2021 年的讨论](https://lists.linuxfoundation.org/pipermail/lightning-dev/2021-October/003307.html)关于改善这种用户体验，提出了几个关于允许转发节点为接收节点保留支付直到接收方已知在线的想法。该讨论中最佳描述的无需信任方法需要使用 [PTLCs](https://bitcoinops.org/en/topics/ptlc/)，截至2022 年底，PTLCs 还未被加入 LN。另一种[方法](https://bitcoinops.org/en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments)，可以在现有协议中实现，涉及使用蹦床中继。

## Optech 新闻简报和网站提及

**2023**

* [使用适配器签名证明接受了异步支付](https://bitcoinops.org/en/newsletters/2023/02/01/#ln-async-proof-of-payment)
* [请求证明异步支付被接受](https://bitcoinops.org/en/newsletters/2023/01/25/#request-for-proof-that-an-async-payment-was-accepted)
* [非交互式通道开放承诺的想法可能允许异步支付快速再平衡](https://bitcoinops.org/en/newsletters/2023/01/11/#non-interactive-ln-channel-open-commitments)
* [Eclair #2464 添加了一个用于允许一个节点向同行交付异步支付的有用触发器](https://bitcoinops.org/en/newsletters/2023/01/04/#eclair-2464)

**2022**

* [2022 年度回顾：异步支付](https://bitcoinops.org/en/newsletters/2022/12/21/#async-payments)
* [Eclair #2435 添加了当使用蹦床中继时支持基本形式的异步支付](https://bitcoinops.org/en/newsletters/2022/10/05/#eclair-2435)
* [蹦床路由和移动支付](https://bitcoinops.org/en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments)

**2021**

* [支付离线节点](https://bitcoinops.org/en/newsletters/2021/10/20/#paying-offline-ln-nodes)

## 参见

* [蹦床支付（Trampoline Payments）](https://bitcoinops.org/en/topics/trampoline-payments/)
* [PTLCs](https://bitcoinops.org/en/topics/ptlc/)
* [适配器签名（Signature Adaptors）](https://bitcoinops.org/en/topics/adaptor-signatures/)
* [支付证明（Proof of Payment）](https://bitcoinops.org/en/topics/proof-of-payment/)
