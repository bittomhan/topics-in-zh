# 暂存发票 - Hold invoices



**暂存发票**是闪电网络（LN）上的一种发票，在接收到付款后，接收方并不立即释放原像（preimage）。相反，接收方会先执行某些操作，然后要么接受付款，明确拒绝它，或者让它超时。

例如，Alice 可以在她的网站上自动生成暂存发票，但在客户实际支付之前不检查库存中请求的商品。这将给她一个机会，在无法交付时取消付款。

暂存发票有时也被拼写为“hodl invoices”。

## 主要代码和文档

* [暂存发票](https://github.com/lightningnetwork/lnd/pull/2022)

## Optech 新闻简报和网站提及

**2020**

* [关于双向费用的讨论，以允许对暂存发票收费](https://bitcoinops.org/en/newsletters/2020/11/04/#bi-directional-upfront-fees-for-ln)
* [Zap 0.7.0 Beta 添加了对暂存发票的支持](https://bitcoinops.org/en/newsletters/2020/07/22/#zap-0-7-0-beta-released)
* [逆向预付款可能改善暂存发票的成本分摊](https://bitcoinops.org/en/newsletters/2020/02/26/#reverse-up-front-payments)

**2019**

* [LND #3390 通过单独的 HTLC 跟踪简化了暂存发票逻辑](https://bitcoinops.org/en/newsletters/2019/09/11/#lnd-3390)
* [C-Lightning #2540 添加钩子，允许插件实现暂存发票](https://bitcoinops.org/en/newsletters/2019/04/16/#c-lightning-2540)
* [LND #2022 合并，添加了对暂存发票的支持](https://bitcoinops.org/en/newsletters/2019/03/19/#lnd-2022)

## 参见

* [通道堵塞攻击](https://bitcoinops.org/en/topics/channel-jamming-attacks/)
