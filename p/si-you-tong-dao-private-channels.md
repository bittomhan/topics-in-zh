---
description: 也涵盖未公布的通道（Unannounced channels）
---

# 私有通道 - Private channels

**未公布的通道**是指未向网络广告其用于路由的闪电网络（LN）通道。

大多数未公布的通道被认为属于不打算路由支付的用户，例如移动客户端的用户，他们并非始终在线以路由支付。

另一种名称是**私有通道**，但专家之间存在争议，关于这些通道是否[提高隐私](https://arxiv.org/pdf/1909.02717.pdf)或[不提高](https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-December/002408.html)，因此使用普遍接受的名称“未公布的通道”可能更为合适。

## Optech 新闻简报和网站提及

**2023**

* [LND v0.17.0-beta 附带对未公布的 taproot 和 MuSig2 LN 通道的实验性支持](https://bitcoinops.org/en/newsletters/2023/10/04/#lnd-v0-17-0-beta)

**2021**

* [C-Lightning #4611 更新了 `keysend` RPC 以支持未公布的通道](https://bitcoinops.org/en/newsletters/2021/07/21/#c-lightning-4611)

**2020**

* [C-Lightning #3623 在路由支付时改进未公布通道的隐私](https://bitcoinops.org/en/newsletters/2020/04/22/#c-lightning-3623)
* [C-Lightning #3600 添加了盲路径以提高未公布通道的隐私](https://bitcoinops.org/en/newsletters/2020/04/08/#c-lightning-3600)
* [打破 UTXO 和未公布通道之间的联系](https://bitcoinops.org/en/newsletters/2020/01/29/#breaking-the-link-between-utxos-and-unannounced-channels)
* [Eclair #1283 允许多路径支付通过未公布的通道](https://bitcoinops.org/en/newsletters/2020/01/22/#eclair-1283)
* [C-Lightning #3351 增强了 `invoice` RPC 以用于私有通道](https://bitcoinops.org/en/newsletters/2020/01/08/#c-lightning-3351)

**2019**

* [关于 LN 拓扑和缺乏关于未公布通道的公开信息的讨论](https://bitcoinops.org/en/newsletters/2019/09/18/#lightning-network-topology)
* [C-Lightning #2234 为 `invoice` RPC 添加了私有通道的路由提示](https://bitcoinops.org/en/newsletters/2019/01/22/#c-lightning-2234)
* [C-Lightning #2230 向 `listpeers` RPC 添加了一个 `private` 标志](https://bitcoinops.org/en/newsletters/2019/01/15/#c-lightning-2230)

**2018**

* [LND #1944 调整了 `sendtoroute` RPC，允许通过私有通道路由](https://bitcoinops.org/en/newsletters/2018/11/13/#lnd-1944)

## 参见

* [盲路径](https://bitcoinops.org/en/topics/rendez-vous-routing/)
