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

# {StarryDesert}

1. 自我介绍

   2024年应届生，干过java，新入行web3小白，参加过sui的黑客松并获奖(虽然只是入围奖)。

2. 你认为你会完成本次残酷学习吗？

   我觉得我会

## Notes

<!-- Content_START -->

### 2024.12.10

笔记内容

#### 初识 Arbitrum

Arbitrum是一种基于以太坊（Ethereum）的Layer 2扩容解决方案，旨在提高以太坊网络的交易处理能力和降低交易成本。

##### 使命

1. 保证以太坊的安全性和去中心化，利用主网作为最终的安全层。
2. 提升用户的体验，开发者无需更多的学习成本，便能轻松且快速的部署和迁移合约。
3. 减少主网的负载，做到了降低交易费用和提高交易速度。

#### 核心机制：Optimistic Rollup

1. **批量处理**：将多个交易合并成一个单一的交易，让多个交易被打包压缩以压缩数据的方式存储在主网上，这样可以有效的减少主网的交易负载，降低交易费用
2. **欺诈证明**：乐观的假设链上的Arbitrum 上的活动均为合法的，如果有验证者质疑某比交易的合法性，可以提交声明，启动挑战。一但该比交易的欺诈行为被确认，则此交易会被回滚，并惩罚恶意的验证者
3. **使用Off-chain的链下计算**：Arbitrum上交易的计算都在链下进行，然后将计算的结果提交到以太坊主网。通过这种方法提高了交易的处理能力并降低了交易成本

#### 今日总结

通过今天的学习，我对Arbitrum和其核心机制的Optimistic Rollup有了初步的了解，认识到其在以太坊扩容解决方案中的重要性和潜力。

### 2024.12.11

笔记内容

#### Rollup, ZK Rollups与Optimistic，Arbitrum的区别

1. **Rollup**：是一种整理方法，将一堆交易任务送到Layer2协议去处理，从而提升以太坊的运行效率。
2. **ZK Rollups**：是一种利用零知识证明的密码学算法，在无需知道验证者是谁的情况下，完成外包工作的Layer2方法。适合Payment等需要快速交易的业务，但算法稍复杂。
3. **Optimistic Rollups**：是一种利用一堆验证者，在默认所有打包均为合法的情况下，通过奖惩机制，监督发掘是否有Bug的Layer2方法。
4. **Optimistic，Arbitrum**：两者都是以**Optimistic Rollups**协议为基础开发的项目，但具体有以下不同：
   - **验证机制**：**Optimistic** 只进行一轮欺诈证明，而**Arbitrum**进行多轮欺诈证明。
   - **交易执行**：**Optimism**的交易计算依靠Layer 1来执行，而**Arbitrum**的交易则在其自己的虚拟机中执行，无需依赖Layer 1。
   - **虚拟机**：**Arbitrum**有自己的虚拟机，更加兼容ETH网络，而**Optimism**则依赖Layer 1的虚拟机。

### 2024.12.12

笔记内容

#### Arbitrum的仲裁机制

- 当验证者对某比交易发起挑战时，**挑战管理器**（**ChallengeManager**）将仲裁挑战游戏，通过对全局状态（包括块哈希）进行二分来缩小挑战范围，直到挑战仅剩下一个块。

- 挑战状态机有三个阶段：**Block challenge**、**Execution challenge**和**oneStepProveExecution**。
  - **Block challenge**：挑战首先将全局状态（包括区块哈希）一分为二。在对实际的机器执行提出争议之前，争议将缩小到单个区块。一旦挑战被一分为二到单个区块，当前响应者就可以调用 `challengeExecution`。
  - **Execution challenge**：一旦缩小到单个区块，就可以将实际的机器执行一分为二。一旦执行被平分为单个步骤，当前响应方就可以调用`oneStepProveExecution`。
  - **oneStepProveExecution**：当前响应方必须提供校样数据才能执行计算机的某个步骤。如果执行该步骤以与之前断言不同的状态结束，则当前响应方将赢得质询。

- **General bisection protocol**：涉及对任何程度的分割，当前回应者必须选择相邻的两个段来挑战，并提供一个起始段等于第一个段但结束段不同于第二段的二分。

  - 挑战的程度是指段哈希的数量减一，一个段和下一个段之间的距离根据程度和段长度计算。
  - 挑战的进展是通过确保每个二分都具有至少 `min(40, numStepsInChallengedSegment)` 的度数，以确保挑战取得进展。

  - 赢得挑战使当前回应者成为赢家的对手，设置状态哈希为 0，从而结束游戏。

#### 交互式欺诈证明的特点

1. **高效性**：交互式证明可以解决大于一笔交易的争议，减少了对L1区块的空间占用，降低了rollup成本。
2. **灵活性**：交互式证明允许实现上的更大灵活性，例如加入EVM中还不存在的指令。
3. **无合约大小限制**：交互式证明无需为每一个L2合约创建一个以太坊合约，所以也不要求合约符合以太坊合约的限制。
4. **低复杂度**：交互式证明只需检查**"Alice"**和**"Bob"**的操作**在往正确的方向走**，而不需要模拟一整笔交易的执行。
5. **高交易级gas limit**：交互式证明可以处理大gas容量的Arbitrum交易，即使一笔交易gas消耗量太大，也仍有可能可以放进Arbitrum的区块内。

   这些特点使得交互式证明成为**Arbitrum**的核心设计，并使得**Arbitrum**能够高效、灵活地解决争议和执行交易。

### 2024.12.13

笔记内容

#### **Arbitrum One**

Arbitrum One是Arbitrum的第一个版本，其架构部分在L1（以太坊主网），部分在L2（Arbitrum链）。它使用EthBridge来仲裁Arbitrum Rollup协议，并维护Arbitrum Rollup在以太坊链上的收件箱和发件箱。用户可以通过以太坊链上的收件箱和发件箱将交易发送至Arbitrum链，并观察这些交易的结果。Arbitrum虚拟机（AVM）是EthBridge提供的功能，是L1和L2之间的网关。

#### **Nitro**

Nitro是Arbitrum One的技术栈升级，它的费用更低、以太坊兼容性更好以及zk证明更简洁。Nitro采用多轮欺诈证明，通过证明者和验证者之间的多轮交互来确保系统的安全性和正确性。Nitro还采用了用Go语言重写的节点软件Geth，实现了以太坊高度兼容。Nitro的证明系统是交互式欺诈证明，通过二分查找找到引起分歧的那个区块的第一个操作码。

#### **Nova**

Nova是基于AnyTrust技术搭建的新链，专为游戏、社交应用程序和对成本更敏感的用例而设计。Nova提供了两种数据发布方式，一种是像Nitro一样以Calldata的形式发布完整数据，另一种是发布DACert证明数据的可用性。Nova的定序器将完整的数据集同时发送给所有DAC委员会的成员，委员会签名后把带有签名的证明返回给定序器，定序器收集到足够多的证明就能将它们聚合并创建有效的数据可用性证明（DACert），然后把DACert发布到主网。如果定序器没有收集到足够多的证明，Nova会回退到Rollup模式（以Calldata形式发布数据到主网）。

#### **AnyTrust**

AnyTrust是Arbitrum扩容方案最初的构想，是Arbitrum Nitro的技术变式。它通过最小信任假设来降低calldata的交易成本，依靠外部数据可用性委员会来存储数据并按需提供。AnyTrust与Rollup的区别在于AnyTrust引入了数据可用性委员会，将原本应该存储在inbox合约中的calldata数据转移到链下的数据可用性委员会存储。

#### **Arbitrum L3战略**

Arbitrum团队推出了Arbitrum Orbit，一个开发框架，允许用户使用任何基于Arbitrum Rollup的L2网络作为结算层来创建和启动L3网络。Arbitrum Orbit允许用户在隐私、权限、费用代币、治理等方面定制自己的链。基于Arbitrum Orbit，Arbitrum团队推出了XAI，一个游戏专用L3网络，拥有专用的计算和存储资源。XAI将原生受益于Arbitrum的技术堆栈：Nitro+BOLD+Stylus。

### 2024.12.14

### Arbitrum Nitro的核心功能

1. **高级数据压缩**：
   - Nitro通过优化数据的存储和传输，显著减少了在Layer 1上发布的交易数据量。这种压缩技术降低了每笔交易的成本，使得在Arbitrum网络上进行交易更加经济高效。
2. **执行与故障证明的分离上下文**：
   - Nitro将交易的执行和故障证明过程分开处理。执行上下文专注于快速处理交易，而故障证明上下文则用于验证交易的正确性。这种分离提高了Layer 1节点的性能，降低了交易费用，并确保了系统的高效运行。
3. **以太坊L1燃气兼容性**：
   - Nitro确保其定价和会计系统与以太坊L1完全兼容。这样，开发者和用户可以在Nitro上运行未修改的EVM合约和以太坊交易，简化了迁移和操作的复杂性，同时保持了与以太坊主网的无缝集成。
4. **安全的重试机制**：
   - Nitro设计了安全的重试机制，以消除重试票据创建失败的风险。这意味着在交易未成功完成时，用户可以安全地重试操作，而不会面临丢失资金或状态不一致的问题。
5. **Geth追踪**：
   - Nitro集成了Geth的追踪功能，增强了调试支持。这使得开发者能够更轻松地跟踪和分析交易执行过程中的状态变化，帮助识别和解决潜在问题。

### Nitro的核心设计原则

1. **排序和确定性执行**：
   - Nitro采用两阶段策略处理交易：首先对交易进行排序，然后通过确定性状态转换函数执行这些交易。这样的设计确保了交易结果的可预测性，任何节点都可以独立验证交易的结果。
2. **与Geth的集成：
   - Nitro的核心代码基于go-ethereum（Geth），确保了与以太坊的高度兼容性。通过直接使用Geth的库，Nitro能够利用以太坊的现有数据结构和格式，从而简化开发和提高效率。
3. **执行与证明的分离：
   - Nitro使用相同的源代码进行交易执行和证明，但针对这两种情况分别编译为本地代码和WebAssembly（WASM）。这种设计优化了性能，使得在执行时可以获得更高的速度，而在证明时则可以确保安全性和可移植性。
4. **乐观Rollup与交互式欺诈证明**：
   - Nitro采用乐观Rollup协议，允许任何验证者在Layer 1上发布其声称正确的Rollup块，并为其他人提供挑战的机会。通过交互式欺诈证明机制，Nitro能够高效地解决交易结果的争议，确保系统的安全性和可靠性。



<!-- Content_END -->
