# 哈希时间锁合约 - Hash Time Locked Contract, HTLC

**哈希时间锁合约** 是一种在闪电网络（LN）支付通道、跨链原子交换、同链硬币交换、零知识条件支付以及其他合约协议中使用的条件付款方式。

HTLC 有两个基本条款：一个使用_哈希锁_保护的付款条款和一个使用_时间锁_保护的退款条款。为了打开哈希锁并领取付款，接收方需要公开合约中编码的哈希摘要的原像（preimage）。为了打开时间锁并接收退款，支出方需要等到合约中编码的特定时间之后。

因为公开的原像和过去的时间并不唯一地标识应该接收付款的人，所以只有当 HTLC 还要求一个与支出方（退款接收方）或预期接收方的公钥相匹配的唯一签名时，HTLC 才是安全的。这使得最小的 HTLC 在 [Minsc](https://min.sc/) 脚本语言中看起来像这样：

`(pk(Receiver) **&&** sha256(H)) **||** (pk(Refundee) **&&** older(10))`

## 历史

哈希锁和时间锁作为独立功能明确设计在比特币的原始版本中。据我们所知，最早结合这两者来创建条件付款——我们现在称之为 HTLC——是 2012 年 7 月的一系列帖子（[1](https://bitcointalk.org/index.php?topic=91843.msg1011956#msg1011956), [2](https://bitcointalk.org/index.php?topic=91843.msg1011980#msg1011980)）。然而，一个 [2010 年 12 月的帖子](https://bitcointalk.org/index.php?topic=1790.msg28917#msg28917) 可能在提及“加密上 \[…] 无风险交易”时暗指了相同的基本概念。

## 未来

[时间点锁定合约（Point Time Lock Contracts, PTLCs）](https://bitcoinops.org/en/topics/ptlc/)执行与 HTLCs 相同的功能，但可以提供更好的隐私保护，使用更少的区块空间，并防止路由拦截。作为缺点，它们依赖于[适配器签名（signature adaptors）](https://bitcoinops.org/en/topics/adaptor-signatures/)，这些只能使用比特币现有的 ECDSA 签名实现，要么使用特别慢的算法，要么进行额外的安全假设，或者使用一个不节省多少区块空间的 `OP_CHECKMULTISIG` 构造。如果比特币增加了[斯诺签名（schnorr signatures）](https://bitcoinops.org/en/topics/schnorr-signatures/)，安全性和空间节省之间的这种冲突将得到解决。如果这种情况发生，预计只需要比特币支持的协议可能会从使用 HTLCs 转向使用 PTLCs。其他将比特币与其他加密货币连接的协议可能会继续使用 HTLCs，因为 SHA256 等标准化哈希函数得到了广泛支持。

## Optech 新闻简报和网站提及

**2023**

* [使用契约聚合 HTLC](https://bitcoinops.org/en/newsletters/2023/11/08/#htlc-aggregation-with-covenants)
* [针对 HTLC 的替换周期攻击](https://bitcoinops.org/en/newsletters/2023/10/25/#replacement-cycling-vulnerability-against-htlcs)
* [提议的 OP\_EXPIRE 操作码可能有助于减轻 HTLC 交易固定问题](https://bitcoinops.org/en/newsletters/2023/10/25/#op-expire)

**2021**

* [为 taproot 更新闪电网络：从 HTLCs 转向 PTLCs](https://bitcoinops.org/en/newsletters/2021/09/01/#preparing-for-taproot-11-ln-with-taproot)
* [HTLCs 的隐私问题](https://bitcoinops.org/en/newsletters/2021/08/25/#privacy-problems-with-htlcs)
* [Eclair #1738 将多个 HTLC 执行合并为单个交易](https://bitcoinops.org/en/newsletters/2021/03/31/#eclair-1738)

**2020**

* [2020 年回顾：将闪电网络从 HTLCs 切换至 PTLCs](https://bitcoinops.org/en/newsletters/2020/12/23/#ptlcs)
* [2020 年回顾：HTLC 挖矿激励](https://bitcoinops.org/en/newsletters/2020/12/23/#concern-about-htlc-mining-incentives)
* [CVE-2020-26896：LND 中过早泄露原像](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26896-improper-preimage-revelation)
* [盗取使用 `SIGHASH_SINGLE` 创建的 HTLC 中包含的费用](https://bitcoinops.org/en/newsletters/2020/09/16/#stealing-onchain-fees-from-ln-htlcs)
* [LND #4527 允许用户限制挂起 HTLC 的最大数量](https://bitcoinops.org/en/newsletters/2020/09/02/#lnd-4527)
* [关于挖掘 HTLC 的激励的讨论](https://bitcoinops.org/en/newsletters/2020/07/01/#discussion-of-htlc-mining-incentives)
* [针对接受过多 HTLC 的通道的闪电网络费用勒索攻击](https://bitcoinops.org/en/newsletters/2020/06/24/#ln-fee-ransom-attack)
* [使用节点内存池中的不一致性攻击 HTLC 的原子性](https://bitcoinops.org/en/newsletters/2020/04/29/#new-attack-against-ln-payment-atomicity)

**2019**

* [使用日蚀攻击阻止节点正确处理 HTLC](https://bitcoinops.org/en/newsletters/2019/12/18/#discussion-of-eclipse-attacks-on-ln-nodes)
* [C-Lightning #2858 限制挂起 HTLC 的最大数量以减少成本](https://bitcoinops.org/en/newsletters/2019/08/14/#c-lightning-2858)
* [Stuckless Payments：可在接受前撤销的 HTLC 的想法](https://bitcoinops.org/en/newsletters/2019/07/03/#stuckless-payments)
* [使用 taproot/tapscript 与 HTLCs 的示例](https://bitcoinops.org/en/newsletters/2019/05/14/#complex-spending-with-taproot)
* [关于 HTLCs 是否适用于小额支付的问题](https://bitcoinops.org/en/newsletters/2019/04/30/#do-htlcs-work-for-micropayments)- [Lightning Loop：使用 HTLCs 进行链上 / 链下交换的新工具](https://bitcoinops.org/en/newsletters/2019/03/26/#loop-announced)

## 参见

* [比特币维基中的哈希时间锁合约](https://en.bitcoin.it/wiki/Hash\_Time\_Locked\_Contracts)
* [BIP199](https://github.com/bitcoin/bips/blob/master/bip-0199.mediawiki)
* [时间点锁定合约（Point Time Locked Contract, PTLC）](https://bitcoinops.org/en/topics/ptlc/)
