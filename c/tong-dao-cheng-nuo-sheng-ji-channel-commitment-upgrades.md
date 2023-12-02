# 通道承诺升级 - Channel Commitment Upgrades

**通道承诺升级**是对闪电网络（LN）中使用的链上承诺交易格式的更改，或任何可能影响承诺交易的更改。由于涉及通道的双方节点需要完全一致地同意承诺格式，因此对这些更改升级 LN 协议需要格外小心。

此类性质的升级在升级后的承诺交易无法直接从建立通道的设置交易中支出时也可能具有挑战性。例如，最初的 LN 协议通过向设置交易中的 P2WSH 输出付款来建立通道。相比之下，LN 协议可能稍后期望承诺交易从 [taproot](https://bitcoinops.org/en/topics/taproot/) P2TR 输出中支出。处理这种过渡的最简单方法是 P2WSH 用户关闭他们的通道并使用 P2TR 重新打开它们，但这样做会浪费资源，因此开发者致力于不需要不必要通道关闭的通道承诺升级机制。

## 主要代码和文档

* [BOLT 2: 在重建时升级协议](https://github.com/lightning/bolts/pull/868)
* [动态承诺](https://lists.linuxfoundation.org/pipermail/lightning-dev/2022-March/003531.html)

## Optech 新闻简报和网站提及

**2022**

* [更新 LN 承诺](https://bitcoinops.org/en/newsletters/2022/04/06/#updating-ln-commitments)

**2021**

* [C-Lightning #4532 添加了升级通道的实验性支持](https://bitcoinops.org/en/newsletters/2021/06/09/#c-lightning-4532)

**2020**

* [升级通道承诺格式](https://bitcoinops.org/en/newsletters/2020/07/29/#upgrading-channel-commitment-formats)

## 参见

* [锚定输出（Anchor Outputs）](https://bitcoinops.org/en/topics/anchor-outputs/)
* [LN-Symmetry（Eltoo）](https://bitcoinops.org/en/topics/eltoo/)
* [PTLCs](https://bitcoinops.org/en/topics/ptlc/)
