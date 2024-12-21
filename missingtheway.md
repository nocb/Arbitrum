---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# Tomas

1. Hi，大家好，我是一个社区新人，之前一直在关注共学这一种形式，这次鼓起勇气参与这次社区共学活动，希望可以通过学习提升自己。
2. 你认为你会完成本次残酷学习吗？我已经做好完成的准备。

## Notes

<!-- Content_START -->

### 2024.12.10
# Arbitrum

> Arbitrum网络是Ethereum网络的扩展网络，它设计出来的目的就是为了扩展Ethereum并解决Ethereum网络中的一些问题。在Arbitrum网络中你可以做一切你可以在Ethereum网络中做的事情，使用web3App，部署智能合约。但是，使用Arbitrum 你的交易的手续费会更低，你交易所花费的时间会更少。其依靠的核心的核心机制是Optimistic Rollup protocols（乐观假设）其将大部分交易移到链下执行，降低交易成本提高吞吐量。同时其安全性依靠Ethereum主网，保证了安全性。
> 

**The Arbitrum Rollup mechanism adopts an “innocent until proven guilty” attitude.**

***Arbitrum的核心机制为 Arbitrum Rollup*** 

# Some introduction about Arbitrum

> [https://docs.arbitrum.io/welcome/arbitrum-gentle-introduction](https://docs.arbitrum.io/welcome/arbitrum-gentle-introduction)
> 

## Why do we need Arbitrum?

因为以太坊的TPS（transactions per second）太低，大概只有20到40，达到上限后用户进行竞争导致交易fee上涨，而设计导致其瓶颈已经很难提升。

## Why does Ethereum have a low TPS?

因为以太坊就是设计决定，必须要在所有节点上同步交易，并确保其可行性（分布式账本），其势必会影响j交易的并发性和交易速度。

## How does Arbitrum solve the problem?

Arbitrum 通过引入Layer 2 网络和 Arbitrum RollUp 来解决这个问题，Arbitrum Rollup 是作为Ethereum 子模块运行的，与传统意义上的L1交易不同，我们不需要在Ethereum节点上处理每一笔Arbitrum交易，相反，Ethereum采用了一种：**“innocent until proven guilty”  在证明其有罪前其即是无罪的理论。当违规操作出现时，争议处可以被反驳，如果反驳成功无效的交易被忽视，欺诈者会被采取经济惩罚；**

这种引入链下的操作极大的增加了TPS，提高交易速度，减少交易过程中产生的 gas fee。

## Who does this work to prove fraud?

> 把Arbitrum chain状态推向L1，并且对其他有可能不正确的声明提出质疑的叫做 **vaildator**
> 

**vaildator** 并没有权限限制，只要可以运行节点，并且愿意质押一定数量的Ether，都可以成为 **vaildator 。此外只要有一个诚实的节点那么就可以确保这条链是安全的。因为一个vaildator可以抓到任意数量的欺诈者，这也大大增强了其中的安全性。**

# How exactly is Fraud Proven? (欺诈行为是如何被证明的)

当两个validator 产生了不同的判断，最多只有一个 validator 是诚实的。在冲突发生的情况下，他们会进行一个交互游戏 **ChallengeManager** 这个游戏会逐渐缩小冲突范围，直到缩小到一个简单的计算，例如两数相加。这是在L1中进行的，并且会证明其中有一方说的是真话。

### 2024.12.11

今天按照https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat 上的方法搭建了，Dapp并使用本地节点进行了部署。

# RollUp的作用

Roll up 译为压缩整理，Roll up 的作用就是将区块链上需要计算的内容Copy到以太坊之外的Layer2协议进行计算。然后再将结果结果信息打包发送到链上网络。
ZK RollUp 引入了零知识证明，通过复杂严谨的逻辑验证方法进行验证。来认证不同数据的真实性，验证完成后将存有大量签名的数据存入区块链网络。

### 2024.12.12

RollUp将大量的计算放到了L2进行，而L2一般是在一个单台服务器上也叫做 Sequencer（排序器）的地方运行的。Sequencer 在感官上接近于中心化服务器，在RollUp中进行大量运算后，Sequencer会把交易后的状态推给 L1 链，这节省了很多在L1链上处理交易的时间，也降低了gasFee。

RollUp 扩容可以概括为两点：

**成本优化：**其运行在单台服务器上，效率得到了大大提高，降低了交易成本。

**安全保障：**其将交易过程及交易完成后的状态都同步到了L1链，其可以通过只能合约来校验状态的有效性。同时以太坊中还会保存L2中的历史记录，即使 Sequencer 宕机也可以还原出完整的交易记录。
### 2024.12.13
今天阅读了《前Arbitrum技术大使解读Arbitrum的组件结构》的两篇文章，让我对RollUp的ChallengeManager机制，和OP RollUp有了更深层次的理解，今天由于时间问题先暂时不写总结了，明天阅读原生文档后再行补充。
### 2024.12.14
Arbitrum One是典型的OPR，它部署在L1上的合约，并不主动验证提交过来的数据，乐观地认为这些数据没有问题。如果提交的数据有错误，L2的验证者节点会主动发起挑战。
因此OPR也暗含一条信任假设：任意时刻⾄少有⼀个诚实的L2验证者节点。⽽ZKR的合约则通过密码学计算，主动但低成本地验证排序器提交的数据。
## 排序器Sequencer：
接收用户交易并进行排序，计算交易结果，并迅速（通常<1s）返还给用户回执。用户往往在几秒内就能看到自己的交易在L2上链，体验就如同Web2平台。
同时，排序器还会在以太坊链下即时广播最新产生的L2 Block，任何一个Layer2节点都可以异步的接收。但此时，这些L2 Block不具备最终确定性，可以被排序器回滚掉。
每隔几分钟，排序器会将排序后的L2交易数据进行压缩，聚合成批次（Batch），提交至Layer1上的收件箱合约SequencerInbox，以保证数据可用性和Rollup协议的运转。一般而言，被提交至Layer1上的L2数据无法回滚，可以具备最终确定性。
## Arbitrum Rollup协议：
定义Rollup链的区块 RBlock 的结构，链的延续方式，RBlock的发布，以及挑战模式流程等⼀系列的合约。注意，这⾥说的Rollup链并不是大家理解的Layer2账本，而是Arbitrum One为了施展欺诈证明机制，而独立设置的一条抽象出来的“链状数据结构”。
⼀个RBlock可以包含多个L2区块的结果，⽽且数据也迥异，它的数据实体 RBlock 存储在RollupCore的⼀系列合约中。如果⼀个 RBlock 存在问题，Validator将⾯向该RBlock的提交者对其进⾏挑战。
### 2024.12.16
## ChallengeManager
假如验证者A提出Rollup Block到L1上，而B不同意，对其进行挑战。
在B发起挑战后，ChallengeManager合约负责验证对挑战步骤的细分过程：
1.细分是一个双方轮流互动的过程，一方对某个Rollup Block中包含的历史数据进行分段，另一方指出是哪部分数据片段有问题。类似于二分法（实际是N/K）不断渐进缩小范围的一个过程。
2.之后，可以继续定位至哪条交易及结果有问题，再进一步细分至该交易中有争议的某条机器指令。
3.ChallengeManager合约只检查对原始数据进行细分后，产生的『数据片段』是否有效。
4.当挑战者和被挑战者定位到了将被挑战的那条机器指令后，挑战者调用oneStepProveExecution()，发送单步欺诈证明，证明这条机器指令的执行结果有问题。
单步证明最终证明的是WAVM指令集中的单步指令，当合约拿到对应的单步指令后，会与RollUp Block中的指令进行对比，如果不同则挑战成功，如果相同则挑战失败。
### 2024.12.17
## Any Trust Chain
使用Any Trust Chain 可以显著的降低交易的手续费，其与Roll up 网络不同，它并没有采用和Roll up 一样的去中心化/无需信任/无需认证的安全措施，与Roll up 不同，它并没有把全部数据打包上传到L1网络上，它是一种链下的处理方案。当遇到问题时，其会转换为Roll up 模式，使用Any Trust Chain 时必须要有两个验证者保持为诚实的。对于那些需要非常高的交易吞吐量和并不需要严格去中心化的应用，Any Trust Chain 将是一个非常好的选择。
在Arbitrum网络中，Arbitrum One 为 Roll up 网络，Arbitrum Nova 为 Any Trust Chain 网络。
### 2024.12.18
**Ethereum 的扩容策略主要分为以下几点：**

- 分区扩容策略（sharding）：把Blockchain 分片分块，以增加主链上的交易吞吐量和速度，降低费用，但是，由于Roll up 的发明，以及其优秀的能力导致，分片策略并不能成为以太坊扩容的最优解。但是，其仍然对共识机制更简单起到了正面作用。
- Layer 2 ：在主网的基础上引入了二层网络，二层网络多数采用Roll up机制，将二层网络中的数据打包发送到主网，这种将大量的交易处理放到链下的方式大大提升了交易吞吐量，交易速度，降低了GasFee。

Roll up 的优点：

- 大大降低了交易的手续费，提高了速度，吞吐量
- 降低了主网的压力
- 继承了与以太坊主网相同级别的安全措施

Roll up 的缺点：

- 由于Roll up 的节点可能不是完全去中心化的，其节点可能处在被某些独立组织，第三方组织，或像ETH主网一样的组织中的控制当中，这当然有一定的安全性风险。不过通过validator,sequencer等机制可以保证交易的安全性。

**Roll up 类型：**

ZK Rollup , Optimistic Rollup 和 Arbitrum Rollup 的不同之处：

- ZK Rollup 采用了Zero Knowledge 的方式进行验证，通过对状态进行验证，保证交易的正确性，零知识证明不需要知道具体的交易细节，只需要验证状态正确即为交易诚实。
- Optimistic Rollup 采用了 Fraud Proof 以乐观的态度对待，提交到L1链上的数据，经过7天的验证期后可以完成提款。
- Arbitrum Rollup 同样采用了 Fraud Proof，其与Optimistic Rollup 的核心区别是，Arbitrum Rollup 在争议产生的时候，Arbitrum Rollup 采用多步处理策略也就是 Challenge Manager ，会从区块开始一直分割，知道定位到一条WAVM的指令，与L1链上的 Rollup 进行对比验证。Optimistic Rollup 在产生争议时会进行整个交易的验证，更费时间。
### 2024.12.20
## Arbitrum 技术路线图

> Arbitrum 是由 Offchain Labs 发布的L2链，Offchain Labs 始终坚持一个规则进行技术路线的规划：**Your Chain, Your Rules.** 使用Arbitrum技术允许用户及社区拥有构建自己链的能力，社区拥有自治的权利。
> 

首先Arbitrum 将会通过Stylus 方式适配使用不同语言来编译WASM ，例如 Rust ，C ，C# ，通过 Stylus 你可以高效执行代码并节省智能合约消耗的Gas费，使用Stylus你的计算资源和内存成本会大大降低。

## 去中心化

Arbitrum 在未来会逐步落实去中心化的实施将去中心化落到实处，比如实现如下功能：

- ***BoLD* (H2 2024)**
- ***Censorship Timeout* (H2 2024)**
- ***Decentralized Sequencer* (likely 2025)**

## 水平扩展

- ***Fast Withdrawals (Q3 2024)***
- Chain Cluster ***(2025)***

## 性能和效率

- ***Multi-client support* (H1 2025)**
- ***Adaptive Pricing (H1 2025)***

## 引入零知识证明

- ***ZK+Optimistic Hybrid Proving***
<!-- Content_END -->
