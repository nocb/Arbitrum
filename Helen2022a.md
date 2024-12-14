---
timezone: Asia/Shanghai
---

# Helen

1. 自我介绍
    拥有多年的web2后端开发经验，想开拓下web3领域
2. 你认为你会完成本次残酷学习吗？
    会

## Notes

<!-- Content_START -->

### 2024.12.13

Arbitrum是一种基于Optimistic Rollup技术的以太坊Layer2 扩展解决方案，旨在解决以太坊上的拥堵和高gas费问题。

Arbitrum是以太坊的辅助链。运行原理简单说就是Arbitrum 将很多交易一起打包，在Arbitrum链上先进行结算，然后再将交易数据提交给以太坊主链。
Arbitrum采用了一种叫做Optimistic Rollup的技术，它可以将大量的交易打包成一个区块，并提交到以太坊主链上，只有在出现争议时才需要验证区块的正确性。这样可以大幅减少对以太坊主链的资源占用，提高交易吞吐量和速度。

ARB是Arbitrum网络的原生Token，采用的标准是以太坊ERC-20，是Arbitrum网络的治理和激励Token，主要用于奖励验证节点、参与网络治理等。
ARB只是一个治理token，不用于支付Arbitrum链上的任何费用。目前，用户在Arbitrum链上交互支付的Gas费仍是ETH

### 2024.12.14

## Rollup ZK Rollup
Rollup的作用，就是将以太坊需要计算的内容复制，发送到以太坊之外连接的Layer2协议进行计算。然后，将结果信息压缩打包整理，重新发回到链上网络，从而提升以太坊的运行效率。而压缩包中，存有大量的签名确认信息。原先链上每笔交易一个Block里面只能有一个确认Sign签名，而现在这个块等于压缩了很多笔交易签名的VIP签名块。VIP一个过了，等于100个过了。这就间接将ETH的TPS大幅提升。

Rollup Layer 2协议决定了以太坊的安全性

ZK Rollups, ZKSnark 或者叫Zero Knowledge Rollups，是指一种利用零知识证明的密码学算法。
ZKSnark的四大特点：
1. Zero Knowledge: 验证者无需看到交易所有数据
2. Succinct: 言简意赅的，简练的
3. Non-Interactive: 无需知道验证者是谁 
4. Argument of Knowledge: 证明交易的真实性与正确性

Zk Rollups的核心方法，即通过严谨复杂的验证算法，Layer 2协议中的验证者（ZkSnarker/ Validator ）来认证不同数据的真实性(Validity Proof)，从而将认证结果打包。

任何人都可以参与网络认证，成为认证者，所以，本质上来说，ZKSnark也是一种PoW共识机制的Layer 2协议。

## Optimistic Rollups Layer2 

开始认为所有发送的交易都是值得信赖认证过的。Layer 2验证者需要先质押Token作为保证金，如果验证过程中，别人发现了有问题的打包，那么该验证者（Sequencer）将被罚款部分Token，并把其作为奖励给发现问题的人。 

每次数据打包后，会有验证期，以供其他验证者检查是否有问题，是否需要重新退回打包。 

Optimistic Rollups也具有智能合约功能，可以拥有相应的治理Token

Op Rollups与ZK Rollups方法本质的区别是，ZK所有人都可以参与通过PoW认证来参与认证，而OP里面更倾向于选择一组值得信赖的认证者，监督整个打包交易的过程。

Optimism和Arbitrum本质上都是利用乐观型Optimistic Rollup模式的Layer 2协议项目
Arbitrum在验证时，进行多轮fraud proofs.同时，Aribitrum的交易，并不在Layer1上进行执行，并且有自己的虚拟机，更加兼容ETH网络。

目前的ZK Rollups更适合Payment等需要快速交易的业务，算法稍复杂；而Optimistic类方法更适合Dapp开发与Defi业务，就是提币时间有点长

<!-- Content_END -->
