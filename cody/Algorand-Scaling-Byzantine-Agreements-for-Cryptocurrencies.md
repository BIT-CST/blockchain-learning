# Algorand: Scaling Byzantine Agreements for Cryptocurrencies







> **WHITE PAPERS**: <https://www.algorand.com/technology/white-papers>



<details>
<summary> WHITE PAPERS </summary>

Algorand is dedicated to fostering constant evolution to anticipate and fulfill future technology needs on our platform. Our researchers represent some of the best and brightest in blockchain and cryptocurrency. Recent research that has been peer reviewed and edited is found below.

DEC 03, 2019

* [Pixel: Multi-signatures for Consensus](https://www.algorand.com/technology/white-papers)

By Manu Drijvers, Sergey Gorbunov, Gregory Neven and Hoeteck Wee

In Proof-of-Stake (PoS) and permissioned blockchains, a committee of verifiers agrees and sign every new block of transactions. These blocks are validated, propagated, and stored by all users in the network. However, posterior corruptions pose a common threat to these designs, because the adversary can corrupt committee verifiers after they certified a block and use their signing keys to certify a different block. Designing efficient and secure digital signatures for use in PoS blockchains can substantially reduce bandwidth, storage and computing requirements from nodes, thereby enabling more efficient applications.

We present Pixel, a pairing-based forward-secure multi-signature scheme optimized for use in blockchains, that achieves substantial savings in bandwidth, storage requirements, and verification effort. Pixel signatures consist of two group elements, regardless of the number of signers, can be verified using three pairings and one exponentiation, and support non-interactive aggregation of individual signatures into a multi-signature. Pixel signatures are also forward-secure and let signers evolve their keys over time, such that new keys cannot be used to sign on old blocks, protecting against posterior corruptions attacks on blockchains. We show how to integrate Pixel into any PoS blockchain. Next, we evaluate Pixel in a real-world PoS blockchain implementation, showing that it yields notable savings in storage, bandwidth, and block verification time. In particular, Pixel signatures reduce the size of blocks with 1500 transactions by 35% and reduce block verification time by 38%.

This paper was peer-reviewed and will appear at USENIX Security 2020. The paper can be viewed [here](https://eprint.iacr.org/2019/514).

FEB 24, 2019

* [Vault: Fast Bootstrapping for the Algorand Cryptocurrency](https://algorandcom.cdn.prismic.io/algorandcom%2F5392df3a-6dda-41f4-a6ea-3330c2be0634_vault.pdf)

By Derek Leung, Adam Suhl, Yossi Gilad, Nickolai Zeldovich

Abstract: Decentralized cryptocurrencies rely on participants to keep track of the state of the system in order to verify new transactions. As the number of users and transactions grows, this requirement becomes a significant burden, requiring users to download, verify, and store a large amount of data to participate. Vault is a new cryptocurrency design based on Algorand that minimizes these storage and bootstrapping costs for participants. Vault’s design is based on Algorand’s proof-of-stake consensus protocol and uses several techniques to achieve its goals. First, Vault decouples the storage of recent transactions from the storage of account balances, which enables Vault to delete old account state. Second, Vault allows sharding state across participants in a way that preserves strong security guarantees. Finally, Vault introduces the notion of stamping certificates, which allow a new client to catch up securely and efficiently in a proof-of-stake system without having to verify every single block. Experiments with a prototype implementation of Vault’s data structures show that Vault’s design reduces the bandwidth cost of joining the network as a full client by 99.7% compared to Bitcoin and 90.5% compared to Ethereum when downloading a ledger containing 500 million transactions.

The peer reviewed white paper can been viewed [here](https://eprint.iacr.org/2018/269).

AUG 28, 2018

* [Algorand Agreement - Super Fast and Partition Resilient Byzantine Agreement](https://algorandcom.cdn.prismic.io/algorandcom%2F218ddd09-8d6f-42f7-9db9-5cfbc0aedbe5_algorand_agreement.pdf)

By Jing Chen, Sergey Gorbunov, Silvio Micali, Georgios Vlachos

Abstract: We present a simple Byzantine agreement protocol with leader election, that works under > 2/3 honest majority and does not rely on the participants having synchronized clocks. When honest messages are delivered within a bounded worst-case delay, agreement is reached in expected constant number of steps when the elected leader is malicious, and is reached after two steps when the elected leader is honest. Our protocol is resilient to arbitrary network partitions with unknown length, and recovers fast after the partition is resolved and bounded message delay is restored. We will briefly discuss how the protocol applies to blockchains in a permissionless system. In particular, when an honest leader proposes a block of transactions, the first voting step happens in parallel with the block propagation. Effectively, after the block propagates, a certificate is generated in just one step of voting.

This white paper has been published [here](https://eprint.iacr.org/2018/377).

OCT 31, 2018

* [Algorand: Scaling Byzantine Agreements for Cryptocurrencies](https://algorandcom.cdn.prismic.io/algorandcom%2Fa26acb80-b80c-46ff-a1ab-a8121f74f3a3_p51-gilad.pdf)

By Yossi Gilad, Rotem Hemo, Silvio Micali, Georgios Vlachos, Nickolai Zeldovich

Abstract: Algorand uses a new Byzantine Agreement (BA) protocol to reach consensus among users on the next set of transactions. To scale the consensus to many users, Algorand uses a novel mechanism based on Verifiable Random Functions that allows users to privately check whether they are selected to participate in the BA to agree on the next set of transactions, and to include a proof of their selection in their network messages. In Algorand’s BA protocol, users do not keep any private state except for their private keys, which allows Algorand to replace participants immediately after they send a message. This mitigates targeted attacks on chosen participants after their identity is revealed.

We implement Algorand and evaluate its performance on 1,000 EC2 virtual machines, simulating up to 500,000 users. Experimental results show that Algorand confirms transactions in under a minute, achieves 125x Bitcoin’s throughput, and incurs almost no penalty for scaling to more users.

This whitepaper has been peer edited and reviewed and is published [here](https://dl.acm.org/citation.cfm?id=3132757).

MAY 26, 2017

* [Algorand Theoretical Paper](https://algorandcom.cdn.prismic.io/algorandcom%2Fece77f38-75b3-44de-bc7f-805f0e53a8d9_theoretical.pdf)

By Jing Chen, Silvio Micali

Abstract: A public ledger is a tamperproof sequence of data that can be read and augmented by everyone. Public ledgers have innumerable and compelling uses. They can secure, in plain sight, all kinds of transactions —such as titles, sales, and payments— in the exact order in which they occur. Public ledgers not only curb corruption, but also enable very sophisticated applications —such as cryptocurrencies and smart contracts. They stand to revolutionize the way a democratic society operates. As currently implemented, however, they scale poorly and cannot achieve their potential. Algorand is a truly democratic and efficient way to implement a public ledger. Unlike prior implementations based on proof of work, it requires a negligible amount of computation, and generates a transaction history that will not “fork” with overwhelmingly high probability.

This whitepaper has been peer edited and reviewed and is published [here](https://arxiv.org/abs/1607.01341).

</details>



> YouTube 简介视频：
>
> Basic intro to Algorand protocol: <https://www.youtube.com/watch?v=gACVKaNqxPs>
>
> 奖励分布及变化原则：
>
> [Long Term Algo Dynamics](https://algorand.foundation/the-algo/algo-dynamics)
>
> [Demystifying Algorand Rewards Distribution: A Look at How & When Algorand Token Rewards Are Calculated](https://www.purestake.com/blog/algorand-rewards-distribution-explained/)
>
> algorand foundation 里各种资料
>
> <https://algorand.foundation/algorand-protocol/about-algorand-protocol>
>
> <https://algorand.foundation/the-algo/algo-basics>
>
> CSDN 别人的总结：
>
> [【转】共识机制-Algorand共识算法介绍](https://blockchain-fans.blog.csdn.net/article/details/88663443)
>
> [feng_zhiyu：[PaperNotes]2017.Algorand: Scaling byzantine agreements for cryptocurrencies](https://blog.csdn.net/feng_zhiyu/article/details/114646182)
>
> [Anqi： Algorand](https://blog.csdn.net/sanganqi_wusuierzi/article/details/78846430)







# Algorand 简介

Algorand 也是一种类 bitcoin 的电子货币，只不过使用的是 PoS + new Byzantine Agreement（BA★） 来实现的。

Algorand blockchain 没有分叉，分钟级即可确认交易。安全要求是诚实用户拥有 2/3 的钱。

在 BA★ 协议里，使用 VRF 选举一个 commitee 对每一轮进行区块投票，被选举的用户是随机的并且敌手提前不知道谁被选中，用户除了自己的私钥，不保存任何 private state。



> A key technique that makes BA⋆ suitable for Algorand is the use of **verifiable random functions (VRFs)** [38] to randomly select users in a **private and non-interactive way**. BA⋆ was previously presented at a workshop at a high level [37], and a technical report by Chen and Micali [16] described an earlier version of Algorand.



# 挑战

Algorand 设计的时候面临的 **3 个挑战**：

1. **Sybil attacks**

    an adversary creates many pseudonyms to influence the Byzantine agreement protocol. 

2. BA★ **的可扩展性**

    BA★ must scale to millions of users, which is far higher than the scale at which state-of-the-art Byzantine agreement protocols operate.

3. Algorand 抗 **denial-of-service** attacks

    协议能继续进行 even if an adversary disconnects some of the users



## Sybil attacks

为了防止 Sybil attacks，每个用户都有一个权重 weight，weight 基于用户账户里的钱多少，只要 2/3 的钱在 honest users 手上，就能防止 forks 和 double-spending



## BA★ 的可扩展性

通过选举 committee 来实现，委员会的选择和 weight 有关，来保证 committee 的诚实。

> BA★ achieves scalability by choosing a committee—a small set of representatives ran- domly selected from the total set of users—to run each step of its protocol
>
> BA★ chooses committee members randomly among all users based on the users’ weights. This allows Algorand to ensure that a sufficient fraction of committee members are honest.



## DoS 攻击

敌手可能对 committee 成员攻击来操纵选举结果，但是 BA★ 是使用 VRF 来选择 committee，只有 committee 成员开始执行协议的时候攻击者才知道谁是成员。

如果成员在执行协议后被攻击，要求 speak just once，可以很容易实现 Participant replacement，因为用户不保存 private state。

> Finally, an adversary may target a committee member once that member sends a message in BA⋆. BA⋆ mitigates this attack by **requiring committee members to speak just once**. Thus, once a committee member sends his message (exposing his identity to an adversary), the committee member becomes irrelevant to BA⋆. BA⋆ achieves this property by avoiding any private state (except for the user’s private key), which makes all users equally capable of participating, and by electing new committee members for each step of the Byzantine agreement protocol.

<p class="icon question" markdown="1"> 这个 speak just once 没懂怎么做和监控的  </p>



# GOALS AND ASSUMPTIONS

## 2 个 goals

* **Safety goal**

    With overwhelming probability, all users（包括 isolated users that are disconnected from the network） agree on the same transactions.

* **Liveness goal**

    Algorand aims to reach consensus on a new set of transactions **within roughly one minute**

## assumption

诚实用户拥有的钱大于 2/3



### strong synchrony - 实现Liveness goal

大多数诚实用户发送的消息在一个已知的时间内能到达其他诚实用户那里。

只允许敌手操作少部分用户，网络不允许分片。

> most honest users (e.g., 95%) can send mes- sages that will be received by most other honest users (e.g., 95%) within a known time bound. This assumption allows the adversary to **control the network of a few honest users**, but does **not allow the adversary to manipulate the network at a large scale**, and does not allow network partitions

### weak synchrony - 实现 Safety goal

网络可以被敌手控制一段时间（asynchrony period），但是时间有限，该段时间过去后，网络必须变成 strongly synchronous，strongly synchronous 的时间小于 asynchronous 的时间。

> the network can be asynchronous (i.e., entirely controlled by the adversary) for a long but bounded period of time (e.g., at most 1 day or 1 week). After an asynchrony period, the network must be strongly synchronous for a reasonably long period again (e.g., a few hours or a day) for Algorand to ensure safety. More formally, **the weak syn- chrony assumption is that in every period of length b (think of b as a day or aweek), there must be a strongly synchronous period of length s < b** (an s of a few hours suffices)



# overview

## Gossip protocol

用户随机选择一小部分用户通信，使用私钥对发送的消息签名，对同一个消息只会转发一次。

> each user selects **a small random set of peers to gossip** messages to To ensure messages cannot be forged, every message is **signed** by the private key of its original sender; other users check that the signature is valid before relaying it. To **avoid forwarding loops**, users **do not relay the same message twice**. Algorand implements gossip over TCP and **weighs peer selection based on how much money they have**, so as to mitigate pollution attacks.



![image-20210702082727977](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/07/02/image-20210702082727977-082732.png)

## Cryptographic sortition

**VRF**：这个关键还是 VRF 的使用，对于给定的输入 x（这个抽签函数被多次用到，x 在各处都不同），用自己的私钥可以生成一个 hash 和证明 proof，用 proof 和公钥可以验证 hash 是对 x 做的。

> Informally, on any input string x, VRFsk(x) returns two values: **a hash and a proof**. The hash is a hashlen- bit-long value that is **uniquely determined by sk and x**, but is indistinguishable from random to anyone that does not know sk. The proofπ enables anyone that knows pk to check that the hash indeed corresponds to x, without having to know sk. For security, we require that the VRF provides these properties even if pk and sk are chosen by an attacker

sortition 除了 VRF 产生的 hash 和 proof 外，还会生成 j，这里的 j 不同地方意义不一样，可以表示优先级、票数等。

### 抽签

![image-20210702083554350](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/07/02/image-20210702083554350-083556.png)

### 验证

![image-20210702084103705](https://gitee.com/baicaihenxiao/imageDB/raw/master/uPic/png/2021/07/02/image-20210702084103705-084106-084116.png)

## Block proposal

每个用户通过抽签函数来判断自己有没有被选中作为出块者，抽签函数同时为出块者生成了优先级。

由于会生成多个出块者，用户之间会通信一段时间来比较优先级（通信时包括出块者产生的块和被选中的 proof），只保留高优先级的块。



> All Algorand users execute **cryptographic sortition to determine if they are selected to propose a block in a given round**. We describe sortition in §5, but at a high level, **sortition ensures that a small fraction of users are selected at random**, weighed by their account balance, and provides each selected user with a **priority**, which can be compared between users, and a proof of the chosen user’s priority. Since sortition is random, there may be **multiple users selected to propose a bloc**k, and the priority deter- mines which block everyone should adopt. Selected users **distribute their block of pending transactions through the gossip protocol, together with their priority and proof**. To ensure that users converge on one block with high probabil- ity, block proposals are prioritized based on the proposing user’s priority, and users wait for a certain amount of time to receive the block



## BA★

Block proposal 通过一小段时间通信来比较优先级，但是远远不能保证所有用户对同一个 block 达成一致，然后每轮使用抽签函数选举 committee 对 block 投票，直到达成共识。

> Each user initializes BA⋆ with the **highest-priority block that they received**. BA⋆ executes in repeated steps, illustrated in Fig- ure 2. Each step begins with sortition (§5), where all users check whether they have been selected as committee mem- bers in that step. Committee members then broadcast a message which includes their proof of selection. These steps repeat until, in some step of BA⋆, enough users in the com- mittee reach consensus. (Steps are not synchronized across users; each user checks for selection as soon as he observes the previous step had ended.) As discussed earlier, an impor- tant feature of BA⋆ is that committee members do not keep private state except their private keys, and so can be replaced after every step, to mitigate targeted attacks on them.






