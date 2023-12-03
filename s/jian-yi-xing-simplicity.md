# 简易性 - Simplicity

**简易性**是一种正在开发中的低级编程语言，比比特币脚本 (Bitcoin Script) 提供更大的灵活性和表达力。它允许您验证程序的安全性、安全保障和成本。它还提供原生的梅克尔化脚本、正式语义和类型检查。要在比特币上使用简易性，需要进行软分叉，但目前尚未提出这样的提议。目前，ElementsProject.org 和比特币核心 (Bitcoin Core) 代码库的测试分支支持简易性。

简易性的核心由九个称为组合子的原始操作符组成，其语义被正式指定。然而，在如此低级别上实现比特币功能会导致程序庞大、运行缓慢且成本高昂。可以将实现基本功能的预写简易性程序添加到比特币共识中，以便其他简易性程序可以使用短标识符内联这些函数，消除它们的大小惩罚。然后可以用更高效的语言（如C语言）重新实现内联简易性代码的功能，这些代码被证明与纯简易性程序等效——消除速度或内存惩罚。这些替换（称为 _jets_）允许整个程序用简易性语言指定，包括像哈希函数和签名验证这样的操作，但可以使用其他语言的代码执行，以实现与今天的比特币脚本类似的性能。

假设简易性在某个阶段通过软分叉集成到比特币中，并配备了足够的 _jets_，那么像 [SIGHASH\_ANYPREVOUT](https://bitcoinops.org/en/topics/sighash\_anyprevout/) 这样的新功能（目前需要软分叉来实现）可以在比特币上使用，而无需单独的共识规则变更。尽管简易性提供了某些正确性证明，但在设计任何依赖于比特币限制之外的合约协议时，仍然需要小心。

## 主要代码和文档

* [简易性：高保证智能合约](https://blockstream.com/2018/11/28/en-simplicity-github/)

## Optech新闻简报和网站提及

**2022**

* [基于奇亚脚本 (Chia Lisp) 的 BTC-Script 作为简易性的替代方案](https://bitcoinops.org/en/newsletters/2022/03/16/#using-chia-lisp)

**2020**

* [关于将简易性实现为 taproot 叶子版本的讨论记录](https://bitcoinops.org/en/newsletters/2020/08/05/#bip-taproot)
* [关于用简易性实现 taproot 的问题](https://bitcoinops.org/en/newsletters/2020/07/29/#could-we-skip-the-taproot-soft-fork-and-instead-use-simplicity-to-write-the-equivalent-of-taproot-scripts)
* [关于下一代智能合约与简易性的讨论记录](https://bitcoinops.org/en/newsletters/2020/05/06/#simplicity-next-generation-smart-contracting)
* [关于简易性和静态分析的问题](https://bitcoinops.org/en/newsletters/2020/04/29/#how-is-simplicity-better-suited-for-static-analysis-compared-to-script)

## 另见

* [简易性：区块链的新语言](https://blockstream.com/simplicity.pdf)
* [契约 (Covenants)](https://bitcoinops.org/en/topics/covenants/)
