# Miniscript

**Miniscript** 是一种允许软件自动分析脚本的方法，包括确定为了花费由该脚本保护的比特币必须生成哪些见证数据（witness data）。通过 Miniscript，钱包能够知道需要做什么，钱包开发者在从一个脚本模板切换到另一个时不需要编写新代码。

Miniscript 提供的比特币脚本的结构化表示允许钱包在使用的脚本上更加灵活。为支持这种灵活性，可以使用易于编写的策略语言创建 Miniscripts。策略是可组合的，允许任何有效的子表达式被另一个有效的子表达式替换（在比特币系统施加的某些限制内）。

## 主要代码和文档

* [交互式 Miniscript 演示](http://bitcoin.sipa.be/miniscript/)

## Optech 新闻简报和网站提及

**2023**

* [现场报告：Miniscript 之旅](https://bitcoinops.org/en/wizardsardine-miniscript/)
* [Bitcoin Core #27255 将 miniscript 移植到 tapscript，提供 tapscript 描述符](https://bitcoinops.org/en/newsletters/2023/10/18/#bitcoin-core-27255)
* [Bitcoin Core #26567 使用 miniscript 和描述符计算输入重量以进行费用估算](https://bitcoinops.org/en/newsletters/2023/09/13/#bitcoin-core-26567)
* [MyCitadel v1.3.0 增加对 miniscript 的更高级支持](https://bitcoinops.org/en/newsletters/2023/05/24/#mycitadel-wallet-adds-enhanced-miniscript-support)
* [Bitcoin Core #24149 为基于 P2WSH 的 miniscript 描述符输出增加签名支持](https://bitcoinops.org/en/newsletters/2023/02/22/#bitcoin-core-24149)

**2022**

* [2022 年回顾：Bitcoin Core 中的 miniscript 描述符](https://bitcoinops.org/en/newsletters/2022/12/21/#miniscript-descriptors)
* [Bitcoin Core #24148 为包含 miniscript 的描述符添加仅观察支持](https://bitcoinops.org/en/newsletters/2022/07/20/#bitcoin-core-24148)
* [关于描述符支持 miniscript 的 PR 审查俱乐部](https://bitcoinops.org/en/newsletters/2022/06/08/#bitcoin-core-pr-review-club)
* [为硬件签名设备调整描述符和 miniscript](https://bitcoinops.org/en/newsletters/2022/05/18/#adapting-miniscript-and-output-script-descriptors-for-hardware-signing-devices)
* [Bitcoin Core #24147 为 miniscript 增加后端支持](https://bitcoinops.org/en/newsletters/2022/04/13/#bitcoin-core-24147)

**2021**

* [Specter-DIY v1.5.0 增加对 miniscript 的支持](https://bitcoinops.org/en/newsletters/2021/04/21/#specter-diy-v1-5-0)

**2020**

* [Miniscript 的正式规范](https://bitcoinops.org/en/newsletters/2020/12/02/#formal-specification-of-miniscript)
* [Miniscript 对安全性的警告或失败，当混合使用时间 / 高度锁时](https://bitcoinops.org/en/newsletters/2020/09/23/#research-into-conflicts-between-timelocks-and-heightlocks)
* [更新 PSBT 规范以改善 miniscript 兼容性](https://bitcoinops.org/en/newsletters/2020/08/26/#bips-955)
* [基于 miniscript 的新支出策略语言 Minsc](https://bitcoinops.org/en/newsletters/2020/08/05/#new-spending-policy-language)
* [关于 miniscript 策略语言规范的问题](https://bitcoinops.org/en/newsletters/2020/03/25/#where-can-i-find-the-miniscript-policy-language-specification)

**2019**

* [2019 年回顾：miniscript](https://bitcoinops.org/en/newsletters/2019/12/28/#miniscript)
* [Miniscript 征求意见](https://bitcoinops.org/en/newsletters/2019/08/28/#miniscript-request-for-comments)
* [Miniscript 开发的洞见：最终堆栈为空](https://bitcoinops.org/en/newsletters/2019/05/29/#final-stack-empty)
* [Miniscript 演讲](https://bitcoinops.org/en/newsletters/2019/02/05/#miniscript)

## 参见

* [Miniscript：简化的比特币脚本](https://medium.com/blockstream/miniscript-bitcoin-scripting-3aeff3853620)
