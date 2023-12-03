# 蹦床支付 - Trampoline payments

**蹦床支付**是一种提议中的支付方式，其中支付者将支付路由到一个中间节点，该节点可以选择到最终接收者的剩余路径。

使用单个蹦床节点会向其透露目的地。为了恢复隐私，支付者可能需要要求通过多个蹦床节点路由支付，以便没有一个节点知道它们是将支付路由到最终接收者还是只是另一个中间蹦床节点。

尽管允许蹦床节点选择部分路径可能需要支付更多的路由费用，但这意味着支付者不需要知道如何向任意节点路由支付——支付者知道如何向任何兼容蹦床的节点路由支付就足够了。这对于无法追踪完整网络图的轻量级 LN 客户端来说是有优势的，因为它们经常离线或在性能不足的移动硬件上运行。

## 主要代码和文档

* [通过蹦床支付外包路由计算](https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-March/001939.html)

## Optech 新闻简报和网站提及

**2022**

* [Eclair #2435 添加了对蹦床中继的基本异步支付的支持](https://bitcoinops.org/en/newsletters/2022/10/05/#eclair-2435)
* [关于将蹦床路由与首跳支付保留相结合的讨论](https://bitcoinops.org/en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments)

**2021**

* [LN 开发者会议总结，包括讨论蹦床支付](https://bitcoinops.org/en/newsletters/2021/11/10/#ln-summit-2021-notes)
* [Electrum 4.1.0 添加了对蹦床支付的支持](https://bitcoinops.org/en/newsletters/2021/05/19/#electrum-4-1-0-enhances-lightning-features)

**2019**

* [2019 年年终回顾：蹦床支付](https://bitcoinops.org/en/newsletters/2019/12/28/#trampoline)
* [Eclair #1209 添加了对蹦床洋葱格式的实验性支持](https://bitcoinops.org/en/newsletters/2019/11/20/#eclair-1209)
* [BOLT PR 和关于蹦床支付的讨论](https://bitcoinops.org/en/newsletters/2019/08/07/#trampoline-payments)
* [LN 的蹦床支付](https://bitcoinops.org/en/newsletters/2019/04/02/#trampoline-payments-for-ln)

## 参见

* [BOLTs PR #654：蹦床路由](https://github.com/lightningnetwork/lightning-rfc/pull/654)
