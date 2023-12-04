# 守望塔 - Watchtowers

**守望塔**是一种服务，当它们检测到客户的交易对手发布了过时的通道关闭交易时，会发送 LN 违约补救交易（正义交易）。

守望塔提供的服务允许客户长时间离线，而不必担心资金被交易对手窃取。守望塔不会被委托任何资金，只需负责监控区块链和广播交易，尽管违约补救交易可以设计为在需要守望塔服务时，守望塔会收到部分被保护的资金。

## Optech 新闻简报和网站提及

**2023**

* [LDK #2337 使得使用 LDK 构建守望塔更容易](https://bitcoinops.org/en/newsletters/2023/08/30/#ldk-2337)
* [LND #7069 允许客户要求其守望塔删除会话](https://bitcoinops.org/en/newsletters/2023/04/12/#lnd-7069)
* [守望塔问责证明](https://bitcoinops.org/en/newsletters/2023/04/05/#watchtower-accountability-proofs)
* [在可调节惩罚协议中对守望塔有效使用的描述](https://bitcoinops.org/en/newsletters/2023/03/29/#fn:keychain)

**2021**

* [继承标识符提案与简化守望塔设计的替代方案](https://bitcoinops.org/en/newsletters/2021/10/06/#proposal-for-transaction-heritage-identifiers)

**2020**

* [LND #4782 为使用锚点输出的通道添加守望塔客户端支持](https://bitcoinops.org/en/newsletters/2020/12/09/#lnd-4782)
* [提议存储预签名守望塔交易的服务](https://bitcoinops.org/en/newsletters/2020/07/01/#proposed-service-for-storing-relaying-and-broadcasting-presigned-transactions)
* [关于守望塔协议开发的演讲](https://bitcoinops.org/en/newsletters/2020/07/01/#watchtowers-and-bolt13)
* [C-Lightning #3659 添加对守望塔的支持](https://bitcoinops.org/en/newsletters/2020/05/13/#c-lightning-3659)
* [更新的守望塔 BOLT 规范提案](https://bitcoinops.org/en/newsletters/2020/03/18/#proposed-watchtower-bolt-has-been-updated)

**2019**

* [2019 年终总结：守望塔](https://bitcoinops.org/en/newsletters/2019/12/28/#watchtowers)
* [关于 eltoo 支付通道的守望塔的讨论](https://bitcoinops.org/en/newsletters/2019/12/11/#watchtowers-for-eltoo-payment-channels)
* [提议的守望塔 BOLT 规范](https://bitcoinops.org/en/newsletters/2019/12/04/#proposed-watchtower-bolt)
* [守望塔存储成本](https://bitcoinops.org/en/newsletters/2019/09/25/#watchtower-storage-costs)
* [LND 0.7.0-beta 发布，包括初步的守望塔支持](https://bitcoinops.org/en/newsletters/2019/07/03/#lnd-0-7-0-beta-released)
* [LND PR #3133 添加支持利他主义守望塔的功能](https://bitcoinops.org/en/newsletters/2019/06/19/#lnd-3133)
* [LND PR #2618 实现了私有守望塔支持](https://bitcoinops.org/en/newsletters/2019/03/19/#lnd-2618)
* [LND PR #2448 添加了一个独立的守望塔](https://bitcoinops.org/en/newsletters/2019/01/22/#lnd-2448)
* [LND PR #2439 为守望塔添加了默认策略](https://bitcoinops.org/en/newsletters/2019/01/22/#lnd-2439)

**2018**

* [LND PR #2124 添加了对检测和使用链上花费的支持](https://bitcoinops.org/en/newsletters/2018/11/20/#lnd-2124)
* [LND PRs #1535 和 #1512 为守望塔添加了服务器端通信](https://bitcoinops.org/en/newsletters/2018/10/30/#lnd-1535-1512)
* [LND PR #1543 添加了守望塔版本 0 编码和加密](https://bitcoinops.org/en/newsletters/2018/08/07/#lnd-1543)

## 参见

* [LND 守望塔教程](https://github.com/wbobeirne/watchtower-example)
* [静态通道备份](https://bitcoinops.org/en/topics/static-channel-backups/)
