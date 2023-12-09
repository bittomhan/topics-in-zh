# BIP70 支付协议 - BIP70 payment protocol

**BIP70 支付协议**是一种用于发送支付请求和接收支付的交互式协议。

该协议包括几个步骤：

* 客户点击一个带有附加 `r` 参数（在 [BIP72](https://github.com/bitcoin/bips/blob/master/bip-0072.mediawiki) 中描述）的 [BIP21](https://github.com/bitcoin/bips/blob/master/bip-0021.mediawiki) `bitcoin:` URI。URI 处理程序响应用户的钱包打开请求。
* 钱包联系商家的服务器并请求一个由商家的 SSL 证书签名的支付请求。收到并验证签名的支付请求后，支付细节会自动填写在钱包的_发送交易_屏幕上。可选地，用户会被通知他们正在支付对应签名证书域名的所有者（例如“example.com”）。
* 客户审查支付细节并点击_发送交易_按钮。交易生成并广播到比特币网络。交易的副本发送给商家，商家随后回复确认收到支付（可选地从他们自己的节点重新广播交易）。

与普通 BIP21 URI 相比，该协议有几个优点：

* 商家可以请求支付到任何脚本——不仅仅是流行的地址类型——使该提议与新地址格式兼容。
* 客户的钱包自动发送他们自己的脚本，以防需要发行退款。
* 支付请求有一个过期日期，过了这个日期报价将不再适用。
* 它直接将支付交易交给商家，允许他们广播。这可以让用户通过蓝牙或 NFC 进行支付，即使他们当前没有连接到互联网。

其主要缺点是它要求花费者支持 SSL 证书系统，该系统包括许多在比特币中未使用的算法以及复杂的公钥基础设施 (PKI) 系统。在实践中，这意味着软件需要包含诸如 OpenSSL 这样的库作为依赖项。该库中的漏洞可能被用来利用比特币程序，例如 2014 年可能允许攻击者从比特币核心中访问私钥的 OpenSSL [心脏出血](http://heartbleed.com/)漏洞。

最终，BIP70 未得到广泛采用，几乎所有曾经支持它的商家和钱包要么已经结束支持，要么计划在将来结束支持。

## 主要代码和文档

* [BIP70](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki)
* [BIP71](https://github.com/bitcoin/bips/blob/master/bip-0071.mediawiki)
* [BIP72](https://github.com/bitcoin/bips/blob/master/bip-0072.mediawiki)

## Optech 新闻简报及网站提及

**2021**

* [邮件列表讨论关于 BIP70 替代方案](https://bitcoinops.org/en/newsletters/2021/03/03/#discussion-about-a-bip70-replacement)

**2019**

* [2019 年回顾：比特币核心中 BIP70 的弃用和禁用](https://bitcoinops.org/en/newsletters/2019/12/28/#bip70)
* [比特币核心 0.19 发布，BIP70 支持默认禁用](https://bitcoinops.org/en/newsletters/2019/11/27/#deprecated-or-removed-features)
* [比特币核心 PR#17165 移除对 BIP70 支付协议的支持](https://bitcoinops.org/en/newsletters/2019/10/30/#bitcoin-core-17165)
* [比特币核心 PR#15584 默认禁用 BIP70 支持](https://bitcoinops.org/en/newsletters/2019/09/18/#bitcoin-core-15584)
* [比特币核心 PR#15063 允许将 BIP72 URI 的 BIP21 解析回退](https://bitcoinops.org/en/newsletters/2019/02/19/#bitcoin-core-15063)

**2018**

* [比特币核心 PR#14451 允许在不支持 BIP70 的情况下构建 Bitcoin-Qt](https://bitcoinops.org/en/newsletters/2018/10/30/#bitcoin-core-14451)
* [支付到终端点 (P2EP) 与 BIP70 有类似的元素](https://bitcoinops.org/en/newsletters/2018/08/14/#pay-to-end-point-p2ep-idea-proposed)
