# 离散对数合约 - Discreet Log Contracts, DLCs

**离散对数合约**是一种合约协议，其中两个或更多方同意根据预言机（oracle）确定的某个事件的结果来交换资金。事件发生后，预言机发布对事件结果的承诺，获胜方可利用此承诺来索取他们的资金。预言机不需要知道合约的条款（甚至不需知道已经制定了合约）。

创建和解决合约的交易可以使其与许多其他比特币交易无法区分，或者可以在闪电网络（LN）频道内执行。这使得 DLCs 比其他已知基于预言机的合约方法更为隐私和高效。此外，DLCs 相较于早期基于预言机的方法来说，因为预言机对错误结果的承诺会产生明确的欺诈证据，所以它们被认为更安全。

最初的 DLC 构建专门适用于[施诺尔签名（schnorr signatures）](https://bitcoinops.org/en/topics/schnorr-signatures/)。后来，开发了一个版本，使用与比特币现有 ECDSA 签名方案兼容的[签名适配器（signature adaptors）](https://bitcoinops.org/en/topics/adaptor-signatures/)。

**拼写说明：** 该名称是对_离散_对数问题的双关语，后者赋予了该协议其[安全性](https://en.wikipedia.org/wiki/Discrete\_logarithm#Cryptography)，而 DLC 的增强隐私使合约更为_谨慎_。该想法的原始作者和 DLC 互操作性规范使用的拼写是 _discreet log contracts_。

## 主要代码和文档

* [离散对数合约（原始论文）](https://adiabat.github.io/dlc.pdf)
* [离散对数合约简介](https://github.com/discreetlogcontracts/dlcspecs/blob/master/Introduction.md)
* [离散对数合约互操作性规范](https://github.com/discreetlogcontracts/dlcspecs/)

## Optech 新闻简报和网站提及

**2023**

* [钱包 10101 允许在 LN 和 DLCs 之间集资](https://bitcoinops.org/en/newsletters/2023/07/19/#wallet-10101-beta-testing-pooling-funds-between-ln-and-dlcs)
* [Vault 启用操作码的提案也可能使 DLCs 更高效](https://bitcoinops.org/en/newsletters/2023/01/18/#proposal-for-new-vault-specific-opcodes)

**2022**

* [使用与比特币兼容的 BLS 签名进行 DLCs](https://bitcoinops.org/en/newsletters/2022/08/17/#using-bitcoin-compatible-bls-signatures-for-dlcs)
* [关于如何使用 CTV 或其他约束特性使 DLCs 更高效的讨论](https://bitcoinops.org/en/newsletters/2022/02/02/#improving-dlc-efficiency-by-changing-script)

