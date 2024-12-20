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
2. **与Geth的集成**：
   - Nitro的核心代码基于go-ethereum（Geth），确保了与以太坊的高度兼容性。通过直接使用Geth的库，Nitro能够利用以太坊的现有数据结构和格式，从而简化开发和提高效率。
3. **执行与证明的分离**：
   - Nitro使用相同的源代码进行交易执行和证明，但针对这两种情况分别编译为本地代码和WebAssembly（WASM）。这种设计优化了性能，使得在执行时可以获得更高的速度，而在证明时则可以确保安全性和可移植性。
4. **乐观Rollup与交互式欺诈证明**：
   - Nitro采用乐观Rollup协议，允许任何验证者在Layer 1上发布其声称正确的Rollup块，并为其他人提供挑战的机会。通过交互式欺诈证明机制，Nitro能够高效地解决交易结果的争议，确保系统的安全性和可靠性。

### 2024.12.15

笔记内容

### Arbitrum One

- **架构**: Arbitrum 结合了 L1 和 L2 的组件，其中 L1 的 EthBridge 负责仲裁和维护 Arbitrum Rollup 协议。用户通过以太坊链上的收件箱和发件箱与 Arbitrum 进行交互。
- **存款流程**: 用户向以太坊主网的 `Arbitrum L1GatewayRouter` 合约发送交易，存入 ERC-20 代币，随后在 L2 铸造代币。
- **提款流程**: 用户通过 `L2GatewayRouter` 合约发起提款，经过 Retryable Tickets 的处理后，将代币发送回以太坊。

### 交互型 Rollup

- **类型**: 包括非交互型（如 ZK-Rollup）、单轮交互型（如 Optimistic Rollup）和多轮交互型（如 Arbitrum Rollup）。

- 断言机制

  : 断言者需缴纳保证金并开放挑战窗口，若断言错误则会失去保证金。

  - **单轮交互型**: 挑战者指出错误调用，链上合约验证。
  - **多轮交互型**: 通过交互协议解决争议，降低链上工作量。

### 三、状态更新与押注

- **争议断言**: 参与者提出争议断言，声称将执行特定计算生成新状态哈希。
- **押注机制**: 任何人可在状态后下注，若下注错误则会失去押金。

交互式纠纷解决协议

- **多轮欺诈证明**: 采用二分查找找到争议操作码，最终由链上合约裁决。
- **挑战机制**: 挑战者与被挑战者之间的交互，直到找到争议指令。

### Nitro 升级

- **技术栈升级**: Nitro 降低费用，提高以太坊兼容性，采用 Geth 作为核心。
- **执行与证明分开**: 通过不同代码实现执行和证明，提高效率。

### AnyTrust 拆解

- **数据可用性委员会**: 将 calldata 数据存储在链下，降低交易成本。
- **最小信任假设**: 只需确保至少两名委员会成员诚实。

### Arbitrum L3 战略

- **Arbitrum Orbit**: 允许用户基于 Arbitrum Rollup 创建 L3 网络，提供定制化的链。
- **XAI**: 专为游戏和高性能计算设计的 L3，利用 Nitro 技术栈。
- **BOLD 和 Stylus**: 提高结算状态的效率，支持多语言构建应用程序。

### 2024.12.16

笔记内容

### Arbitrum Nitro概述

Arbitrum Nitro是对经典Arbitrum的重大升级，旨在提升其性能和功能。它主要支持两种用例：Arbitrum Rollup（在Arbitrum One链上使用）和AnyTrust（在Arbitrum Nova链上使用）。

### 核心特性

1. **无信任安全性**：安全性基于以太坊，任何一方都可以验证Layer 2的结果。
2. **以太坊兼容性**：能够运行未修改的EVM合约和以太坊交易。
3. **可扩展性**：将合约的计算和存储从以太坊主链转移，允许更高的吞吐量。
4. **最低成本**：设计和工程旨在最小化L1的Gas占用，从而降低每笔交易的成本。

### Nitro的主要创新

1. **高级数据压缩**：通过减少发布到L1的数据量，进一步降低交易成本。
2. **执行和故障证明的分离上下文**：提高L1节点的性能，从而降低费用。
3. **以太坊L1 Gas兼容性**：使EVM操作的定价和记账与以太坊完全一致。
4. **安全重试**：消除了重试票证未能创建的失败模式。
5. **Geth追踪**：提供更广泛的调试支持。

### 交易处理

- Nitro通过两阶段策略处理交易：首先将交易组织成一个有序序列，然后通过状态转换函数按顺序处理这些交易。
- Sequencer负责将到达的交易放入有序序列并发布。

- 采用交互式证明高效解决争议，过程涉及对声明的细分，将争议缩小到单个执行步骤。

### Rollup协议

- 验证者提出RBlocks，协议根据声明确认或拒绝它们。
- 允许无权限参与，要求验证者在提出声明时提供押金。

### 押金与质押

- 验证者可以质押ETH，必须在提出新RBlock之前质押在前一个RBlock上。
- 押金金额可根据链的性能进行调整。



### 2024.12.16

笔记内容

### 核心理念

- **你的链，你的规则**：Arbitrum致力于为用户和开发者提供一个以他们为核心的区块链生态系统，支持构建强大的链上应用和自我治理的社区。

### 路线图

- **可扩展性**：自2021年8月31日推出以来，Arbitrum在可扩展性方面取得了显著进展，并推出了新的功能，致力于解决用户和开发者面临的可用性和去中心化问题。
- **互操作性**：Arbitrum强调简化与其链的交互，推动更广泛的采用，确保不同链之间的无缝导航。

### 开发者体验和采用

- **Stylus**：新推出的Stylus允许开发者使用编译为WebAssembly（WASM）的语言（如Rust、C和C++）进行编程，拓宽了开发者的选择，同时保持对EVM的支持。
- **即将上线**：Stylus将在Arbitrum Day（即将到来的节日）上线，带来重要的执行层升级，提升开发者和用户体验。

### 去中心化

- **BoLD**：预计在2024年下半年推出，增强安全性并推动Arbitrum向第二阶段rollup发展。
- **审查超时**：这一功能将限制审查者的负面影响，增强Arbitrum链的审查抵抗能力。
- **去中心化排序器**：计划在2025年实现，将交易排序的责任分散到更广泛的网络中。

### 互操作性和水平扩展

- **Arbitrum Orbit**：允许开发者根据特定用例自定义链，推动创新。
- **快速提款**：预计在2024年第三季度推出，允许AnyTrust链绕过确认延迟，快速与母链结算。
- **链集群**：计划在2025年推出，允许多个Orbit链紧密对齐其生态系统和基础设施，减少跨链通信时间。

### 性能和效率

- **多客户端支持**：计划在2025年实现，支持多种执行层客户端，以提高区块生产速度，降低节点运营成本。
- **自适应定价**：预计在2025年推出，根据实际资源使用动态调整gas限制，提高性能和资源利用效率。

### 零知识证明

- **ZK与乐观证明的结合**：研究如何将零知识证明整合到Arbitrum链中，以提高确认速度和互操作性。



### 2024.12.19

笔记内容

#### **Arbitrum 简介**

Arbitrum 是一个 Layer2 扩容解决方案，由 Offchain Labs 团队开发。Offchain Labs  由奥巴马任职期间的前白宫技术官员 Ed Felten 共同创立，另外两位联合创始人为 Steven Goldfeder 和 Harry  Kalodner。

#### **融资历史**

Offchain Labs 在 2019 年 3 月完成由 Pantera Capital 领投的 370 万美元种子轮融资，去年 4 月完成 2000 万美元 A 轮融资，同年 8 月又以 12 亿美元估值完成 1.2 亿美元融资，Lightspeed Venture  Partners 领投。

#### **Arbitrum 进展**

Arbitrum One 主网于去年 8 月份上线，目前已有超过 25 万个独立地址存款。Arbitrum 的总锁仓量为 25.5 亿美元，占据 L2 总锁仓量的近 57%。

#### **DeFi 应用**

Arbitrum 上的 DeFi 应用包括：

- 衍生品：ApeX、Dopex、GMX、Jones DAO、Tracer DAO 等
- 兑换/AMM：SushiSwap、Curve、Uniswap、Balancer、1inch、DODO 等
- 借贷/算法稳定币：Aave、dForce、Hundred Finance、Abracadabra 等
- 流动性服务/收益优化/固定利率：Yearn Finance、Beefy Finance、xToken、Pickle Finance 等



### 2024.12.20

笔记内容

#### $ARB代币概述

`ARB`是一种基于ERC−20标准的治理代币，允许持有者参与**ArbitrumDAO**的链上治理协议。ARB代币由一个智能合约在**ArbitrumOne**上铸造，**ArbitrumOne**是一个Layer2的Arbitrumrollup链。

#### ArbitrumDAO的职责

**ArbitrumDAO**负责管理治理协议（根据宪法定义）和DAO治理的技术。这包括**ArbitrumOne**和**ArbitrumNova**链及其底层协议。

#### 持有$ARB代币的投票权

如果你拥有$`ARB`代币，你可以对影响ArbitrumOne和ArbitrumNova链运行和发展的治理提案进行投票。这包括链升级提案以及如何使用DAO国库中的资金的提案。

投票时，你使用`ARB`代币来表明你的支持或反对。你拥有的`ARB`代币越多，你的投票影响力就越大。这是因为**ArbitrumDAO**的智能合约实现了基于代币权重的投票，即投票的权力由投票者钱包中的代币数量决定。

#### 代币委托

`ARB`代币可以委托给其他钱包。这意味着你可以使用自己钱包中的`ARB`代币投票，也可以使用他人委托给你的$`ARB`代币投票。委托对于那些没有时间定期审查和讨论DAO提案的成员来说非常有用。

#### $ARB代币的供应和铸造

`ARB`代币的初始供应量为100亿。每年最多可以以其供应量的2%`ARB`代币，首次铸造事件将在2024年3月15日之后进行。$`ARB`的铸造事件由DAO通过宪法提案执行。

<!-- Content_END -->
