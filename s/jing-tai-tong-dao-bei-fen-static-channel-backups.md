# 静态通道备份 - Static channel backups

**静态通道备份**是备份文件，仅在闪电网络节点打开或关闭新通道时需要更新。在数据丢失的情况下，它们允许节点尝试从远程对等方获取最新的通道状态。

这种机制允许可能丢失了部分状态的节点鼓励其对等方发起通道关闭。由于对等方应该仍然拥有最新的状态，它可以使用该状态关闭通道，并允许两个节点获得最新的余额。

这种方法确实带来两种风险：

* **公开弱点：**对等方可以猜测出有问题，并尝试通过使用旧状态关闭通道来窃取陈旧节点的资金。但这种风险在很大程度上被闪电网络的惩罚机制所减轻：如果陈旧节点在其备份中有该旧状态的撤销，它可以创建违约补救交易（正义交易），从该通道中夺取所有对手方的资金。因为这个风险，使用 `option_data_loss_protect` 机制的对等方在听到陈旧节点的消息时有动机诚实地使用最新状态关闭通道。
* **共同损失：**如果双方都丢失状态，或者远程对等方变得永久不可用，静态通道备份无法帮助恢复当前通道状态。

## 主要代码和文档

* [BOLT2](https://github.com/lightningnetwork/lightning-rfc/blob/master/02-peer-protocol.md)

## Optech 新闻简报和网站提及

**2023**

* [Core Lightning #5361 为对等方存储备份添加了实验性支持](https://bitcoinops.org/en/newsletters/2023/02/15/#core-lightning-5361)

**2022**

* [Core Lightning 0.12 添加了对静态通道备份的支持](https://bitcoinops.org/en/newsletters/2022/08/24/#core-lightning-0-12-0)

**2021**

* [仅使用 BIP32 种子和 option\_data\_loss\_protect 关闭丢失通道](https://bitcoinops.org/en/newsletters/2021/05/05/#closing-lost-channels-with-only-a-bip32-seed)

**2019**

* [LND #2370 现在在每次打开或关闭新通道时更新 channel.backup 文件](https://bitcoinops.org/en/newsletters/2019/01/29/#lnd-2370)

**2018**

* [C-Lightning #1854 部分实现了 option\_data\_loss\_protect](https://bitcoinops.org/en/newsletters/2018/08/28/#c-lightning-1854)
