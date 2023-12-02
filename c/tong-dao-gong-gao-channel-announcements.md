# 通道公告 - Channel Announcements

**通道公告**是宣布某个通道可用于转发支付的广告。这些广告通过闪电网络（LN）的八卦网络传播。

第一版公告要求想要宣传通道的节点证明它们控制着用于 2-of-2 多签名脚本的 P2WSH 输出的一个未花费交易输出（UTXO）。拟议中的公告升级可能允许使用其他脚本的 UTXO，使得可以宣传使用 [P2TR](https://bitcoinops.org/en/topics/taproot/)、[MuSig2](https://bitcoinops.org/en/topics/musig/) 等技术的通道。还讨论了其他改进，这些改进可能打破 UTXO 与特定通道之间的联系。

## 主要代码和文档

* [BOLT7：P2P 节点和通道发现](https://github.com/lightningnetwork/lightning-rfc/blob/master/07-routing-gossip.md)

## Optech 新闻简报和网站提及

**2023**

* [关于更新通道公告的闪电网络开发者讨论](https://bitcoinops.org/en/newsletters/2023/07/26/#updated-channel-announcements)

**2022**

* [闪电网络开发者会议讨论有关八卦网络更新的内容](https://bitcoinops.org/en/newsletters/2022/06/15/#gossip-network-updates)
* [关于更新八卦协议提案的持续讨论](https://bitcoinops.org/en/newsletters/2022/03/30/#continued-discussion-about-updated-ln-gossip-protocol)
* [更新的八卦协议提案](https://bitcoinops.org/en/newsletters/2022/02/23/#updated-ln-gossip-proposal)

**2019**

* [八卦更新提议](https://bitcoinops.org/en/newsletters/2019/07/17/#gossip-update-proposal)
