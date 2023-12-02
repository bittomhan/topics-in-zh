# 即时通道  - Just-In-Time, (JIT) channels

**即时通道 (JIT channels)**是由服务提供商托管的虚拟 LN（Lightning Network）通道。当首次付款到达该通道时，服务提供商创建一个资金交易，并将付款加入其中，从而形成一个正常的通道。这使新用户能够立即开始通过 LN 接收资金。

即时通道不应与[即时路由 (Just-In-Time routing)](https://bitcoinops.org/en/topics/jit-routing/) 混淆，即时路由是一种重新平衡现有通道的技术，用以接受可能初看需要拒绝的付款。

## 主要代码和文档

* [LSPS2: 即时通道协商 (JIT channel negotiation)](https://github.com/BitcoinAndLightningLayerSpecs/lsp/blob/d812a6481f9ff08cc16ab94807483205040de53b/LSPS2/README.md)

## Optech 新闻简报和网站提及

**2023**

* [LDK #2715 允许接受资金不足的 HTLCs，以支持即时通道创建](https://bitcoinops.org/en/newsletters/2023/11/15/#ldk-2715)
* [LDK #2319 允许资金不足的 HTLCs，以支持即时通道创建](https://bitcoinops.org/en/newsletters/2023/06/28/#ldk-2319)
* [提议扩展 BOLT11 发票，以请求潜艇交换的预付款](https://bitcoinops.org/en/newsletters/2023/06/21/#just-in-time-jit-channels)
* [就 LSPs（Lightning Service Providers）包括 LSPS2: 即时通道的拟议规范征求反馈](https://bitcoinops.org/en/newsletters/2023/05/17/#request-for-feedback-on-proposed-specifications-for-lsps)

**2022**

* [LDK #1835 添加了一个用于拦截 HTLCs 的 SCID（Short Channel ID）命名空间，允许 LSPs 开启即时通道](https://bitcoinops.org/en/newsletters/2022/12/14/#ldk-1835)
