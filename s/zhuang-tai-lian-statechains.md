# 状态链 - Statechains

**状态链**是一种被提议的链下系统，允许用户（例如 Alice）将花费 UTXO（未花费交易输出）的能力委托给另一用户（如 Bob），而 Bob 接着又可以将花费权进一步委托给第三方用户（如 Carol）等。

这些链下委托操作均通过使用 [适配器签名](https://bitcoinops.org/en/topics/adaptor-signatures/)（signature adaptors）和可信第三方的合作来执行，该第三方使用 [eltoo](https://bitcoinops.org/en/topics/eltoo/) 机制和其对每个先前委托操作的了解，以确保每次新委托使用的状态号高于以前使用的任何状态号。这些递增的状态号确保最新代理（Carol）的链上花费可以优先于之前代理（Alice 和 Bob）的花费，前提是可信第三方没有与之前的代理串通来作弊。

除了与被委托的签名者（如之前的代理 Alice 或 Bob）串通外，可信第三方没有任何方式可以窃取资金。被委托的签名者始终可以在链上花费 UTXO 而无需从可信第三方获得许可，这可以说让状态链比联合管理的[侧链](https://bitcoinops.org/en/topics/sidechains/)更加可信。

尽管最初是为基于 [schnorr](https://bitcoinops.org/en/topics/schnorr-signatures/) 的适配器签名而描述，但已有工作将协议适配到基于 ECDSA 的[多签名](https://bitcoinops.org/en/topics/multisignature/)，并使用与[双工微支付通道](https://tik-old.ee.ethz.ch/file/716b955c130e6c703fac336ea17b1670/duplex-micropayment-channels.pdf) 提议类似的递减锁定时间，而非 eltoo。这将使状态链可以在比特币上使用，而不依赖于任何提议的共识变更。

## 主要代码和文档

* [状态链](https://medium.com/@RubenSomsen/statechains-non-custodial-off-chain-bitcoin-transfer-1ae4845a4a39)
* [不使用 eltoo 的基于 ECDSA 的状态链](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-March/017714.html)

## Optech 新闻简报和网站提及

**2023**

* [关于状态链的盲签名 MuSig2 的讨论](https://bitcoinops.org/en/newsletters/2023/08/02/#safety-of-blind-musig2-signing)

**2020**

* [关于多个主题的讨论记录，包括状态链](https://bitcoinops.org/en/newsletters/2020/09/02/#sydney-meetup-discussion)
* [关于看守塔及其对状态链的用途的讨论记录](https://bitcoinops.org/en/newsletters/2020/07/01/#watchtowers-and-bolt13)
* [关于不使用 schnorr 或 eltoo 实现状态链的讨论](https://bitcoinops.org/en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo)

**2019**

* [Bitcoin Core 贡献者会议讨论主题：盲状态链](https://bitcoinops.org/en/newsletters/2019/06/12/#assumeutxo)

## 参见

* [Eltoo](https://bitcoinops.org/en/topics/eltoo/)
* [适配器签名](https://bitcoinops.org/en/topics/adaptor-signatures/)
* [多签名](https://bitcoinops.org/en/topics/multisignature/)
* [签名者委托](https://bitcoinops.org/en/topics/signer-delegation/)
* [侧链](https://bitcoinops.org/en/topics/sidechains/)
