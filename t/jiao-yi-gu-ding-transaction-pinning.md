# 交易固定 - Transaction pinning

**交易固定**是一种方法，通过滥用节点防御攻击的措施，使费用增加变得极为昂贵，这些攻击可能会浪费带宽、CPU 和内存。这可能使多方合约协议（如闪电网络）的费用管理变得更加困难。

例如比特币核心这样的节点允许交易被替换（RBF）或与更高费用的子交易打包（CPFP）时，会对这些替换施加限制，以防止各种拒绝服务攻击。然而，当两个或多个人都有能力提高交易费用时，这就使其中一个人能够在限制之一上_固定_他们的交易版本，并阻止其他参与者使用费用增加。

一些可以被滥用以实现交易固定的限制包括：

* [**BIP125**](https://github.com/bitcoin/bips/blob/master/bip-0125.mediawiki) **RBF 规则 #3** 要求替换交易支付比被替换交易及其所有子交易总费用更高的绝对费用。这可以让攻击者附加一个大型且低费率的交易到他们想要固定的交易上，迫使任何费用增加支付大型子交易的替换费用。例如，根据 2019 年比特币核心的默认设置，攻击者可以要求诚实参与者支付至少 0.001 BTC 来增加一笔交易的费用（在某些情况下甚至更多）。
* **最大包大小限制**阻止 CPFP 被使用，如果一笔交易在内存池中有超过 101,000 vbytes 的子交易或其他后代，或者有超过 25 个后代或祖先。这可以让攻击者通过创建最大数量的子交易来完全阻止费用增加。如果攻击者因其他原因（例如他们运营向用户支付的服务）必须创建这些交易，这种攻击可能是免费的。对于一些双方合约协议（如当前的闪电网络），这通过 [CPFP carve out](https://bitcoinops.org/en/topics/cpfp-carve-out/) 得到缓解。

## Optech 新闻简报和网站提及

**2023**

* [针对 HTLCs 的替代循环攻击创建了类似固定的问题](https://bitcoinops.org/en/newsletters/2023/10/25/#replacement-cycling-vulnerability-against-htlcs)
* [提出了可能帮助缓解 HTLCs 交易固定的 OP\_EXPIRE 操作码](https://bitcoinops.org/en/newsletters/2023/10/25/#op-expire)
* [用 v3 交易中继防止 coinjoin 固定](https://bitcoinops.org/en/newsletters/2023/06/28/#preventing-coinjoin-pinning-with-v3-transaction-relay)
* [关于如何通过要求费用增加支付 500 倍费用来固定交易的问题](https://bitcoinops.org/en/newsletters/2023/04/26/#how-would-an-adversary-increase-the-required-fee-to-replace-a-transaction-by-up-to-500-times)

**2022**

* [实施了提议的短暂锚点以帮助防止固定攻击](https://bitcoinops.org/en/newsletters/2022/12/07/#ephemeral-anchors-implementation)
* [提议的短暂锚点以帮助缓解固定攻击](https://bitcoinops.org/en/newsletters/2022/10/26/#ephemeral-anchors)
* [提议的 v3 交易中继旨在避免固定攻击](https://bitcoinops.org/en/newsletters/2022/10/05/#proposed-new-transaction-relay-policies-designed-for-ln-penalty)
* [使用交易内省的想法来防止 RBF 固定](https://bitcoinops.org/en/newsletters/2022/05/18/#using-transaction-introspection-to-prevent-rbf-pinning)
* [通过允许交易表明后代限制的想法来防止固定](https://bitcoinops.org/en/newsletters/2022/03/16/#ideas-for-improving-rbf-policy)

**2021**

* [CVE-2021-31876 降低了一些固定攻击的预期成本](https://bitcoinops.org/en/newsletters/2021/05/12/#cve-2021-31876-discrepancy-between-bip125-and-bitcoin-core-implementation)

**2020**

* [BOLT5 更新以防止交易固定攻击](https://bitcoinops.org/en/newsletters/2020/12/16/#bolts-803)
* [交易费用赞助提案旨在消除固定](https://bitcoinops.org/en/newsletters/2020/09/23/#transaction-fee-sponsorship)
* [针对 coinswap 协议的固定攻击](https://bitcoinops.org/en/newsletters/2020/09/09/#continued-coinswap-discussion)
* [针对 eltoo 使用固定等攻击](https://bitcoinops.org/en/newsletters/2020/08/12/#discussion-about-eltoo-and-sighash-anyprevout)
* [关于针对 LN 的攻击的讨论，包括交易固定](https://bitcoinops.org/en/newsletters/2020/08/05/#chicago-meetup-discussion)

**2019**

* [提议覆盖一些 BIP125 RBF 条件以避免固定](https://bitcoinops.org/en/newsletters/2019/06/12/#proposal-to-override-some-bip125-rbf-conditions)

**2018**

* [Eltoo 可能不完全可靠，因为交易固定](https://bitcoinops.org/en/newsletters/2018/12/28/#april)
* [什么是交易固定？](https://bitcoinops.org/en/newsletters/2018/11/27/#what-is-transaction-pinning)

## 参见

* [CPFP carve out](https://bitcoinops.org/en/topics/cpfp-carve-out/)
* [短暂锚点](https://bitcoinops.org/en/topics/ephemeral-anchors/)
