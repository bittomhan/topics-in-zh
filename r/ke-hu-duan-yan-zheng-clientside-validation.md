---
description: 也涵盖客户端验证（Client-side validation）、Taro 和 Taproot Assets
---

# RGB

**客户端验证协议**允许比特币交易承诺某些数据，这些数据的有效性是独立于比特币共识规则下交易有效性的。客户端验证可以利用共识规则，例如只允许在有效的区块链中一次性花费一个输出，但它也可能施加只有对验证感兴趣的人知道的额外规则。

一个概念上简单的客户端验证协议可能会将一个代币与特定的 UTXO（未使用交易输出）关联起来。只有一组验证器需要知道这种关联；它不需要发布到区块链或任何公共地方。当 UTXO 被花费时，花费交易将代币与新的 UTXO 关联起来。如果 Alice 目前控制着与代币关联的 UTXO，而 Bob 想从她那里购买，她可以向他提供最初关联的证据，然后他可以使用他验证过的区块链副本加上客户端验证来验证代币从最初到 Alice 手中的每一次转移的历史。他还可以验证 Alice 创建的交易是否正确格式化，以将代币分配给 Bob 控制的 UTXO。

[**RGB**](https://rgb.tech/) 是一个客户端验证协议，使用[支付至合约（pay-to-contract）](https://bitcoinops.org/en/topics/pay-to-contract-outputs/) 让交易承诺附加数据，如转账。该协议设计上极其灵活。

[**Taproot Assets**](https://docs.lightning.engineering/the-lightning-network/taproot-assets/)，原名 **Taro**，是一个深受 RGB 启发的协议，使用 [taproot](https://bitcoinops.org/en/topics/taproot/) 的承诺结构让交易承诺附加数据。Taproot 的结构本身源于支付至合约。如其名称所示，协议的初始开发特别聚焦于资产转移（即，代表资产的数字代币）。

这两个协议都旨在与链下交易兼容，如 LN 支付。类似于 LN 通道的生命周期，一个链上设置交易被发布，承诺代币由参与方共同控制；一系列链下交易各自承诺代币在各方间的当前分配；最终承诺的交易在链上发布。

只有想支持 RGB 或 Taproot Assets 的钱包需要理解这些协议，且只有想发送或接收特定代币或其他客户端验证合约的钱包需要了解那个合约。对其他所有人来说，使用 RGB 和 Taproot Assets 创建的交易看起来像普通的比特币交易。

## Optech 新闻通讯和网站提及

**2023**

* [为 taproot 资产发布的规范](https://bitcoinops.org/en/newsletters/2023/09/13/#specifications-for-taproot-assets)
* [RGB 的更新](https://bitcoinops.org/en/newsletters/2023/04/19/#rgb-update)

**2022**

* [Taro 可转移代币方案](https://bitcoinops.org/en/newsletters/2022/04/13/#transferable-token-scheme)

## 参见

* [支付至合约（P2C）](https://bitcoinops.org/en/topics/pay-to-contract-outputs/)
