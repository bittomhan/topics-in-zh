# 硬件钱包接口 - Hardware Wallet Interface, HWI

**硬件钱包接口**是一个 Python 库和命令行工具，用于使用部分签名的比特币交易（Partially-Signed Bitcoin Transactions, PSBTs）和输出脚本描述符与硬件钱包进行交互。

该工具主要由比特币核心（Bitcoin Core）开发者设计，以允许该软件将硬件钱包作为外部签名器使用，现在 HWI 也被其他钱包使用。

## 主要代码和文档

* [HWI 仓库](https://github.com/bitcoin-core/HWI)

## Optech 新闻简报和网站提及

**2023**

* [Bitcoin Core #21576 允许使用外部签名器的钱包进行 RBF 费用提升](https://bitcoinops.org/en/newsletters/2023/01/04/#bitcoin-core-21576)

**2022**

* [Bitcoin Core #23578 使用 HWI 添加对外部签名 taproot keypath 花费的支持](https://bitcoinops.org/en/newsletters/2022/11/02/#bitcoin-core-23578)
* [BDK #682 为硬件签名设备添加签名功能，使用 HWI 和 rust-hwi](https://bitcoinops.org/en/newsletters/2022/09/07/#bdk-682)

**2021**

* [HWI #475 为 Blockstream Jade 硬件签名器添加支持](https://bitcoinops.org/en/newsletters/2021/12/01/#hwi-475)
* [Bitcoin Core GUI #4 通过 GUI 添加对使用 HWI 外部签名器的初步支持](https://bitcoinops.org/en/newsletters/2021/06/16/#bitcoin-core-gui-4)
* [大幅更新和扩展 HWI 文档](https://bitcoinops.org/en/newsletters/2021/03/03/#hwi-413)
* [Bitcoin Core #16546 添加与 HWI 兼容的外部签名器接口](https://bitcoinops.org/en/newsletters/2021/03/03/#bitcoin-core-16546)

**2020**

* [HWI #363 为 Bitbox02 硬件钱包添加支持](https://bitcoinops.org/en/newsletters/2020/09/09/#hwi-363)
* [Lily Wallet 首次发布支持 HWI](https://bitcoinops.org/en/newsletters/2020/07/22/#lily-wallet-initial-release)
* [修复 segwit 费用过付攻击影响 HWI 兼容性](https://bitcoinops.org/en/newsletters/2020/06/10/#fee-overpayment-attack-on-multi-input-segwit-transactions)
* [BTCPay Vault 使用 HWI 进行签名](https://bitcoinops.org/en/newsletters/2020/02/19/#btcpay-vault-using-hwi-for-signing)

**2019**

* [2019 年回顾：HWI](https://bitcoinops.org/en/newsletters/2019/12/28/#core-hwi)
* [CoreDev.tech 讨论：将 HWI 集成到比特币核心](https://bitcoinops.org/en/newsletters/2019/06/12/#hwi)
* [Bitcoin Core 0.18 支持基本的硬件签名器](https://bitcoinops.org/en/newsletters/2019/05/07/#basic-hardware-signer-support-through-independent-tool)
* [Bitcoin Core 初步硬件钱包支持](https://bitcoinops.org/en/newsletters/2019/02/19/#bitcoin-core-preliminary-hardware-wallet-support)

## 参见

* [部分签名的比特币交易（Partially-Signed Bitcoin Transactions, PSBTs）](https://bitcoinops.org/en/topics/psbt/)
* [输出脚本描述符（Output script descriptors）](https://bitcoinops.org/en/topics/output-script-descriptors/)
* [Miniscript](https://bitcoinops.org/en/topics/miniscript/)
* [防数据泄露的签名（Exfiltration resistant signing）](https://bitcoinops.org/en/topics/exfiltration-resistant-signing/)
