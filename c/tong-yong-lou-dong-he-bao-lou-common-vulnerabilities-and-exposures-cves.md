---
description: >-
  也涵盖 CVE-2012-2459, CVE-2013-2292, CVE-2017-12842, CVE-2017-18350,
  CVE-2018-17145, CVE-2020-26895, CVE-2020-26896, 和 CVE-2021-31876
---

# 通用漏洞和暴露 - CVEs，Common Vulnerabilities and Exposures

**通用漏洞和暴露** 是已被目录化的严重漏洞，旨在帮助开发者、研究人员和公众高效地分享有关潜在威胁的信息。

## 拥有自己专题页面的 CVEs

* [CVE-2018-17144](https://bitcoinops.org/en/topics/cve-2018-17144/) 是一个可能允许攻击者多次花费相同比特币的漏洞。

## 其他 CVEs

* [**CVE-2012-2459**](https://bitcointalk.org/?topic=102395)**:** 可以将一个有效的区块变异为一个无效区块，这个无效区块承诺相同的默克尔根。当比特币核心的易受攻击版本看到这样的无效区块时，它们缓存了其拒绝，因此稍后会拒绝该区块的有效版本，这很容易导致短期网络分区，用户可能被欺骗接受无效的比特币。在比特币 0.6.1 中修复。
  * [CVE-2012-2459: Taproot 标签哈希的部分动机](https://bitcoinops.org/en/newsletters/2019/05/14/#tagged-hashes)
  * [CVE-2012-2459: 与新比特币核心漏洞披露相关](https://bitcoinops.org/en/newsletters/2019/03/12/#bitcoin-core-vulnerability-disclosure)
* [**CVE-2013-2292**](https://bitcointalk.org/?topic=140078)**:** 比特币核心中的一个漏洞，据信可能允许攻击者创建一个需要超过三分钟来验证的区块。建议在 [共识清理（consensus cleanup）](https://bitcoinops.org/en/topics/consensus-cleanup-soft-fork/) 软分叉中修复，尽管提议的解决方案遇到了争议。
  * [CVE-2013-2292: 糟糕的交易验证性能激发共识清理](https://bitcoinops.org/en/newsletters/2019/03/05/#legacy-transaction-verification)
* [**CVE-2017-12842**](https://bitcoinops.org/en/newsletters/2018/12/28/#cve-2017-12842)**:** 允许通过特殊制作的真实 64 字节交易（该交易在区块中得到确认）来创建不存在交易的 SPV 证明。可用于窃取 SPV 客户端，尽管针对 SPV 客户端的其他已知攻击成本更低。建议在 [共识清理（consensus cleanup）](https://bitcoinops.org/en/topics/consensus-cleanup-soft-fork/) 软分叉中修复。
  * [CVE-2017-12842: 讨论最小交易大小](https://bitcoinops.org/en/newsletters/2020/05/27/#minimum-transaction-size-discussion)
  * [CVE-2017-12842: 共识清理软分叉中提议的默克尔树修复](https://bitcoinops.org/en/newsletters/2019/03/05/#merkle-tree-attacks)
  * [CVE-2017-12842: 比特币 SPV 证明中的漏洞](https://bitcoinops.org/en/newsletters/2018/12/28/#cve-2017-12842)
  * [CVE-2017-12842: 讨论降低最小可中继交易大小](https://bitcoinops.org/en/newsletters/2022/10/19/#minimum-relayable-transaction-size)
  * [CVE-2017-12842: 比特币核心 PR 审核俱乐部讨论降低最小可中继交易大小](https://bitcoinops.org/en/newsletters/2022/11/09/#bitcoin-core-pr-review-club)
* [**CVE-2017-18350**](https://bitcoinops.org/en/newsletters/2019/11/13/#cve-2017-18350-socks-proxy-vulnerability)**:** 影响使用 SOCKS 代理的比特币核心用户的漏洞。在比特币核心 0.16.0 中修复。
  * [CVE-2017-18350: SOCKS 代理漏洞的完整披露](https://bitcoinops.org/en/newsletters/2019/11/13/#cve-2017-18350-socks-proxy-vulnerability)
* [**CVE-2018-17145**](https://bitcoinops.org/en/newsletters/2020/09/16/#inventory-out-of-memory-denial-of-service-attack-invdos)**:** 用过量的 `inv` 消息淹没一个节点可能导致节点耗尽内存并崩溃，增加了 [日蚀攻击（eclipse attacks）](https://bitcoinops.org/en/topics/eclipse-attacks/) 的风险，这些攻击可能窃取资金。影响了比特币核心（Bitcoin Core），Btcd，Bcoin 和多个替代币节点。在比特币核心 0.16.2，Btcd 0.21.0-beta 和 Bcoin 1.0.2 中修复。
  * [CVE-2018-17145: inv 内存溢出拒绝服务攻击的完整披露](https://bitcoinops.org/en/newsletters/2020/09/16/#inventory-out-of-memory-denial-of-service-attack-invdos)
* [**CVE-2020-26895**](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26895-acceptance-of-non-standard-signatures)**:** 由于接受非标准的“高 S”签名，在 LND 中的漏洞可能导致通道无法及时关闭，因此可能导致资金被盗。在 LND 0.10.0-beta 中修复。
  * [CVE-2020-26895: BOLTs #807 增加关于非标准签名的警告](https://bitcoinops.org/en/newsletters/2020/11/11/#bolts-807)
  * [CVE-2020-26895: 接受非标准签名的完整披露](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26895-acceptance-of-non-standard-signatures)
* [**CVE-2020-26896**](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26896-improper-preimage-revelation)**:** 由于在回应外部路由请求时不当地透露本地预像（preimages），在 LND 中的漏洞可能导致资金被盗。在 LND 0.11.0-beta 中修复。
  * [CVE-2020-26896: LND #4752 更新预像透露代码](https://bitcoinops.org/en/newsletters/2020/12/02/#lnd-4752)
  * [CVE-2020-26896: BOLTs #808 增加关于不当预像透露的警告](https://bitcoinops.org/en/newsletters/2020/11/18/#bolts-808)
  * [CVE-2020-26896: 不当预像透露的完整披露](https://bitcoinops.org/en/newsletters/2020/10/28/#cve-2020-26896-improper-preimage-revelation)
* [**CVE-2021-31876**](https://bitcoinops.org/en/newsletters/2021/05/12/#cve-2021-31876-discrepancy-between-bip125-and-bitcoin-core-implementation)**:** [BIP125](https://github.com/bitcoin/bips/blob/master/bip-0125.mediawiki)关于可选加入替换费用（Replace By Fee, RBF）的规范表示，一个未确认的父交易如果标志了可替换性，那么任何花费父交易输出的子交易也通过推断继承变得可替换。比特币核心（Bitcoin Core）没有实现这种行为；Btcd 则实现了。
  * [CVE-2021-31876: BIP125 和比特币核心实现之间的差异](https://bitcoinops.org/en/newsletters/2021/05/12/#cve-2021-31876-discrepancy-between-bip125-and-bitcoin-core-implementation)
