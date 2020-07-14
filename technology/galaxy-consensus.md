# Galaxy Consensus 

[Download Galaxy Consensus Paper](https://wanchain.org/files/Wanchain-Galaxy-Consensus-V1.0.pdf)

# Protocol Overview

### Overall Architecture and Process

Galaxy Consensus is an efficient, secure, and practical Proof of Stake consensus protocol proposed in a paper published by Wanchain’s Research & Development team. It was designed to replace the original high-energy PPoW (permissioned proof-of-work) consensus mechanism and to officially open up Wanchain’s consensus mechanism to the wider community as a key step towards complete decentralization. The search for a secure and efficient consensus model has become a major research trend for many blockchain systems. Various models such as PoS, PoA, PoI, etc. have been proposed and debated by the research community. After careful evaluation, Wanchain has developed Galaxy Consensus as a Proof of Stake protocol since we believe that stake should form the basis for on-chain governance and development.

**I. General Background**

There are two core problems which must be solved by any consensus protocol:
> One — deciding who gets to be the block producer (leader selection)
Two — deciding which chain is the valid chain (chain selection)

We can broadly classify different consensus models by how they deal with each of these problems. For example, in traditional PoW such as Bitcoin, leader selection is determined through mining. Since the PoW algorithm requires solving problems based on random hash functions, the only way to find the answer is through brute force computation (in other words, just guessing an innumerable amount of times until the answer is found). Since the answer to the problem is random, no miner can get an advantage over any other in their search for the answer. The probability of winning is only related to how much computing power is thrown at the problem, and is not able to be influenced in some other way, which ensures no one has an unfair advantage.

Chain selection is determined by the longest chain rule. This rule states that whichever chain is longest is considered the valid main chain. In other words, whichever chain has the most computation power dedicated to it is the valid chain. Models which follow this rule are referred to as using “chain based” chain selection. Bitcoin can therefore be described as having a mining (leader selection) + chain based (chain selection) consensus protocol.

A framework such as this one based on mining and the longest chain rule leads to a large amount of wasted energy. This waste is one of the root causes for the introduction of other consensus protocols. So how do today’s mainstream PoS protocol’s attempt to solve this problem?

We will now briefly introduce the PoS consensus mechanisms from three well known public protocols:

[Cardano’s Ouroboros academic paper](https://www.cardano.org/en/academic-papers/) was published at the IACR International Cryptology Conference and is recognized industry wide for its important contributions. Its most outstanding contribution is its introduction of a provably secure consensus model. Amongst the various releases in a series of Ouroboros papers, a number of different ways to choose block producers have been put forth. From initially using random number based selection to anonymous selection using [VRFs (verifiable random functions)](https://en.wikipedia.org/wiki/Verifiable_random_function), Ouroboros gradually improved the security and privacy of the leader selection process. As for chain selection, Ouroboros consistently follows the longest chain rule to guarantee the security of the chain. So the overall framework of Ouroboros is VRF leader selection + chain based.

[Algorand](https://www.algorand.com/docs/whitepapers) is a PoS consensus protocol proposed by Turing Award winner and MIT Professor Silvio Micali. Its most prominent contribution its upgraded BFT (Byzantine Fault Tolerant) protocol — BA★, which uses voting to solve the issue of choosing valid blocks. For choosing block producers and validators Algorand also uses the VRFs to ensure randomness and anonymity. Through the operation of the BA★ protocol, every block of height is confirmed by voting, even if it is empty block, it will still go through the voting process. So Algorand’s overall framework is VRF + BA★ voting.

[Casper](https://github.com/ethereum/wiki/wiki/Casper-Proof-of-Stake-compendium) is a PoS consensus protocol developed for Ethereum. Casper’s advantages lie in its practical betting-style consensus. Validators who have pledged a security deposit can bet on the block that he or she believes will be confirmed. Under the betting rules it is guaranteed that there will only be one unique winning block, and the winning validators will receive a reward. Casper will help Ethereum transition from PoW to PoS, and is a consensus protocol that widely anticipated by the crypto community. In summary Casper’s overall framework is Validator + Betting.

After a brief introduction to several mainstream PoS consensus protocols, we return to Galaxy Consensus. Galaxy Consensus follows a rigorous academic development path, drawing from Ouroboros’ provably safe model. Wanchain’s development team has made a number of improvements to the Ouroboros model, such as an all new efficient and secure random number generation algorithm, as well as an innovative replacement for the VRF algorithm used for leader selection: the Unique Leader Selection (ULS) algorithm. Galaxy Consensus’ ULS algorithm ensures that there is only one unique valid block producer, and greatly reduces the probability of natural forks. Therefore, the overall framework of Galaxy Consensus is ULS + chain based.

### II. Two Types of Nodes

When staking with Wanchain, Validator nodes are divided into two types: Validators who can receive delegations and Validator nodes which cannot receive delegations. In order to allow for holders of smaller amounts of WAN to participate in consensus, the Wanchain team has designed a delegation mechanism based on triple Elliptic Curve Digital Signature Algorithm [(ECDSA](https://en.bitcoin.it/wiki/Elliptic_Curve_Digital_Signature_Algorithm)). Through the delegation mechanism, users holding a small amount of WAN can delegate their rights to Validators, and the Validators participate in consensus on their behalf. Due to the limitation of the signature message space in the ECDSA scheme, Validators can only produce blocks and cannot perform other operations, which ensures the security of users.

With this basic understanding of the delegation mechanism, we can now introduce the difference between the two types of nodes. Each Validator node holds a certain amount of stake, whose value in turn affects the upper limit of the amount of delegations they can receive based on a ratio we will release soon. Non-delegating Validator nodes, on the other hand, are consensus nodes which cannot accept delegation. There is no difference in how the two types of nodes participate in consensus, only in their ability to receive delegations. In order to become a Validator node, a larger amount of WAN must be staked by the node operator than the Non-Delegating node. This mechanism will be described in more detail in later posts.

### III. Ongoing Block Producer Selection Process

In Wanchain Proof of Stake, participating nodes are divided into two groups based on their different tasks: the RNP (Random Number Proposer) group and the EL (Epoch Leader) group. These groups work together to address the two key problems of consensus mentioned above, leader selection and chain selection.

The members of the RNP group are selected according to the proportion of their Staking Power (referred to as Wanstake within the Galaxy yellowpaper) compared to all other nodes. The RNP group is responsible for generating the random numbers to be used by the protocol. The nodes in the RNP group complete the random number generation through the three [distributed key generation (DKG)](https://en.wikipedia.org/wiki/Distributed_key_generation) stages: DKG1, DKG2, and the SIGN stage, ensuring the security of the random number on chain. The secure generation of random numbers is one of the top considerations for maintaining the security of the network. The RNP group is responsible for this critical work, and the random number generated in each round will be used as an important seed for selecting which nodes make up the groups, selecting block producers, and other aspects where random numbers are important to the protocol.

Like the RNP group nodes, the Epoch Leader nodes are selected according to the proportion of each node’s Staking Power compared to all other nodes. The EL group is responsible for collecting transactions and packaging them into blocks through two cycles of work. The first cycle consists of secret message array (SMA) generation through two stages of SMA1 and SMA2, and the sharing of secret data inside the Epoch Leader group. In the second cycle the secret message array is used together with the on chain random number supplied by the RNP group to determine who has the right to propose a block and the time period in which they are responsible for broadcasting the block to the network. The EL group forms the foundation for the secure operation of the protocol.

### IV. Operating Process

After introducing two kinds of Validators and the two groups selected for each cycle, we describe the operating process of Galaxy Consensus from a higher perspective to give you a better understanding. First we introduce two concepts of time: slot and epoch. Readers familiar with Ouroboros should be familiar with these two concepts. The slot is the generation time of a block, that is, a new block is generated in each slot, and an epoch is a time period composed of many consecutive slots. The protocol can be described as a continuously running loop. The following four steps describe the process:

*I. Validators Join the Network*

This is the preparation phase of the protocol. At this stage, all nodes that want to participate in consensus will pledge a certain amount of WAN and select a lock time through a smart contract. The lock time will affect the node’s Staking Power: the longer the total locking time, and the more time has passed during the locking period, the correspondingly higher Staking Power. This design simulates the concept of [coin age](https://en.wikipedia.org/wiki/Proof-of-stake#Coin_age-based_selection) and guarantees the fairness and rationality of stake design and node participation. Once this stage is concluded, many nodes will be eligible to start participating in Wanchain’s network.

*II. Forming the Random Number Proposer and Epoch Leader Groups*

At the beginning of each protocol cycle (epoch), two groups, the RNP group and the EL group, are selected from all validators. The choice of these two groups is based on each node’s Staking Power proportion compared to all other nodes. The random selection process carried out using random numbers on chain in a process similar to [follow-the-satoshi](https://cardanodocs.com/glossary/#follow-the-satoshi). Here we use follow-the-stake-ratio to ensure the fairness of the nodes participating in the formation of the group. The higher the proportion of stake, the greater the chance of being selected to join a group, participating in consensus, and gaining revenue.

*III. RNP group process*

After the RNP group is selected, the nodes in the group complete the three decentralized key generation (DKG) phases of DKG1, DKG2 and the SIGN phase. In the DKG1 phase, each node proposes its own commitment for random number fragment selection, ensuring the immutability of the fragment selection. In the DKG2 phase, each node shares the random number fragments selected by itself to other nodes in the group through [threshold secret sharing](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing). Finally, in the SIGN phase, each node publishes its random number fragment data, completing the generation of random numbers and updating the random number data on the chain. The whole process is guaranteed by threshold secret sharing, as long as the number of online nodes exceeds the threshold, the random number update will be completed smoothly, ensuring the reliability of random number generation. The purpose of this random number is to select the Epoch Leader for each slot.

*IV. EL group process*

After the EL group is selected, it will participate in two cycles of work for each epoch. In the first cycle, the EL group nodes participate in two secret message array (SMA) phases of SMA1 and SMA2. In the SMA1 phase, each node proposes its own secret message’s commitment data, which guarantees the immutability of the secret message. In the SMA2 phase, each node shares their own encrypted secret message with the other nodes to complete the secret message array generation. At the beginning of the second cycle, the nodes in the EL group are sorted according to the random number generated by the RNP group, this sorting is valid throughout the cycle. The block producers are then selected using the secret message array, and the node who has the right to produce the block for each slot is determined. This process is carried out secretly within the EL group, and other nodes outside the group have no way of learning about the results of the selection process. The nodes in the EL group each complete their work of block production according to their right which was determined in the previous step. Whenever a new block is proposed, all the nodes in the EL group must add their own proof of validity. This proof is public and able to be inspected by anyone, ensuring the normal and safe operation of the chain.


# Random Number Generation

### I. The important role random numbers play in blockchain systems:

Before we start digging deeply into the role of random numbers, we need to understand a concept, that is, “entropy”. Entropy is no stranger to those in the field of physics. It is a measure of the degree of chaos in a system. In 1948, Claude Elwood Shannon proposed the concept of information entropy to describe the unreliability of sources. In short, entropy is a measure of uncertainty. To give a simple example: “The weather conditions in Beijing tomorrow” may be sunny, cloudy or rainy, the result is uncertain, so the entropy is positive —however, for the statement, “the earth will be destroyed tomorrow”, we know the earth tomorrow will not be destroyed, so the entropy is zero.

So what is the relationship between entropy and blockchain systems? It can be said that entropy is crucial to blockchain systems and is the security guarantee for the operation of the entire system. Taking Bitcoin as an example, it adopts PoW (Proof of Work) as a consensus algorithm. The miners perform countless hash calculations to compete for the right to be the block producer. The identity of the block producer of any height block cannot be predicted in advance. This is the embodiment of entropy in the Bitcoin system. Imagine if the entropy is 0, that is, the block producers of each block are determined in advance or artificially controllable, then there will be attacks such as collusion and forks. Therefore, any blockchain system needs a safe and effective way to introduce entropy into the system. Blockchain systems based on PoW consensus introduce entropy into the system in a natural way due to the randomness of mining. However, for a blockchain system with PoS or DPoS consensus, it is necessary to design a way to introduce entropy. This is where random number generation algorithms come in. It can be said that the random number generation algorithm is one of the main challenges in designing a proof of stake consensus mechanism, and it is also one of the most important criteria for measuring the merits of the consensus mechanism.

### II. The requirements of a random number generation algorithm:

Since the random number generation algorithm is so important, what should a good random number generation algorithm look like? From a safety and practical point of view, it should meet the following six characteristics:

**1. Decentralized**: The process of generating random numbers is decentralized and does not rely on any trusted third parties.

**2. Unpredictable**: There is no way to predict future random numbers based on historically generated random numbers or other information. This is a basic requirement for randomness.

**3. Unbiased**: No one can use computing power or latecomer advantage to influence the results of random number generation.

**4. Uniformity**: The output of random numbers is evenly distributed within its range.

**5. Guaranteed Output Delivery**: Participants in the random number generation algorithm cannot prevent the random numbers from being generated by violating the algorithm rules, that is, it is guaranteed that there will be a random number output.

**6. Publicly Verifiable**: A node that does not participate in random number generation can monitor the execution of the protocol after execution, ensuring that the random number is trusted and unbiased.

The above six properties are essential for a random number generation algorithm, and any violation of any of them may lead to serious security holes. [According to blockchain security company PeckShield](https://blog.peckshield.com/2018/11/22/eos/), more than 8 gaming projects on EOS have been hacked for over millions of dollars, seriously threatening the EOS ecosystem, and most of the reasons for successful attacks are related to random number generation vulnerabilities. Taking the EOS.WIN project as an example, we analyze the root cause of its random number algorithm vulnerability.

One of the games supported by EOS.WIN is a number guessing game where a user must guess the random number which will be generated by the system. Obviously, if you can influence the random number generation in the system, you can influence the outcome of the game. The factors that determine the random number generation of the EOS.WIN system are the transaction hash ID, the transaction block height, the transaction block prefix, and the global lottery serial number.

Although the transaction block height and the transaction block prefix are the information of some future block, the implementation process specifies that the latest block information currently synchronized is used, and so this information can be pre-determined. Additionally, the transaction hash ID can be combined through the transaction action, and the block data can be pre-computed. With all this information able to be pre-determined, then the generation of the random number depends only on the global lottery serial number.

The attacker then creates many transactions with errors, causing the transaction status to roll back, and in this way controlling the global lottery serial number, thus controlling the generation of the random number until winning. Obviously, EOS.WIN’s random number generation algorithm does not satisfy the second property (unpredictability) and the fourth property (unbiased) mentioned above, so there is a loophole which is ultimately exploitable by an attacker.

### III. Galaxy Consensus random number generation algorithm:

The RNP group in Galaxy Consensus implements a safe and efficient random number generation algorithm by means of commitment, zero-knowledge proof, threshold secret sharing, threshold signatures, elliptic curve-order pairing, etc., and provides data which is the basis for the security of the entire consensus process. In order to be able to illustrate the design of the random number generation algorithm and its subtleties, we compare it to a simple card game:
> **Card Game Description**
> Alice and Bob play a game where each of the two secretly choose a playing card to be placed under the table. After their selection, the card is shown on the desktop. If the sum of the face values of the two cards is even, then Alice wins, if it is odd, Bob wins.

This game may seem simple, but it’s not so easy to be fair on the blockchain. There are many problems we need to overcome to prevent Alice or Bob from cheating. We will analyze them one by one:

**Problem 1**: Alice and Bob can’t change their card selection after making their first choice. Otherwise, they can choose their card according to the other party’s cards. For example, if Alice can change her cards, then Alice can win if she picks a card with the same value as Bob’s, making the sum even.

**Solution:**

Galaxy Consensus ensures that the above cheating does not occur by using a commitment (CM). A commitment is a cryptographic tool that guarantees that “the evidence is retained” without exposing the original data. The commitment data has a one-to-one correspondence with the original data. Anyone can verify the correspondence between the two.

Going back to our example, Alice and Bob each tear a small corner of their chosen playing card and put it on the table. This small corner will not reveal the information of which card they chose, but the unique tear pattern guarantees that they cannot change their card choice without being discovered. In the Galaxy Consensus protocol, this is the DKG1 (Distributed Key Generation) phase of the Random Beacon. Each RNP node calculates the commitment of its selected data and sends it to the chain for verification.

![](media/galaxy1.png)

**Problem 2:** After Alice and Bob choose their playing cards, they must keep their playing cards secret before the official reveal of the cards, and they cannot let any other party see them. At the same time, when the card is shown, it is necessary to prove that the card is indeed the previously selected card, not a newly selected card.

**Solution:**

Galaxy Consensus encrypts the original data using a **p[ublic key encryption algorithm](https://en.wikipedia.org/wiki/Public-key_cryptography)**, and then sends the encryption result to the chain to ensure the confidentiality of the data. At the same time, a [**zero-knowledge proof](https://en.wikipedia.org/wiki/Zero-knowledge_proof)** is used to ensure that the encrypted data of the uplink is fully matched with the commitment. In the Galaxy Consensus protocol, this is the DKG2 phase of the Random Beacon. Each RNP node encrypts the data of other nodes using the other nodes’ public keys and sends it to the chain (S1, S2…SN). At the same time a [DLEQ-Proof (discrete log equivalence proof)](https://blog.cloudflare.com/privacy-pass-the-math/) is also sent on chain, this is used to prove that the encrypted content (S) matches the commitment (CM). After this phase, all nodes can get the data sent by other nodes from the chain and decrypt them locally to plaintext. By way of our previous metaphor of a card game, Alice and Bob lay the torn corners of their cards (CM) out on the table and tape them securely on the table, and then verify (DLEQ) that the cards can be stitched together with the small corners taped to the table to make a complete card (S).

![](media/galaxy2.png)

**Problem 3**: After revealing the card, you need to calculate the points of the two cards. We want to make sure that both Alice and Bob are guaranteed to calculate the same correct result. This problem seems ridiculous, but it is very important. Because a player may be irrational or malicious, and deliberately calculate the wrong number, thus reducing the efficiency of the game.

**Solution:**

Galaxy Consensus solves Problem 3 by using a distributed key generation algorithm, that is, all RNP nodes generate a common group secret key. The key is never produced completely, but is split into key fragments. Each RNP node has a share of the group secret key. After that, the RNP nodes can synthesize the group key signature, and the hash value of the signature is the final random number output. Since the group key is publicly determined, the group key signature is also uniquely fixed. Going back to our card game example, this is how Alice and Bob can be sure to calculate the same value for their cards’ sum.

**Problem 4**: At this point, neither Alice nor Bob can terminate the game. That is, once the game starts, it must end normally, and the game cannot be aborted because a player refuses to cooperate with the rules of the game.

**Solution:**

Galaxy Consensus solves Problem 4 by means of threshold signatures, that is, as long as the participating RNP nodes exceeding the threshold number of participants in the calculation, the group key signature can be synthesized. The refusal of individual RNP nodes to participate in the calculation does not affect the generation of the results. Back to our example of the card game, even if Alice doesn’t want to show up, Bob has the ability to reveal the two cards to complete the game.

The above process corresponds to the SIGN phase of the Random Beacon in the Galaxy Consensus Protocol, in which the RNP nodes cooperate to generate a group key signature and calculate the random number output.

![](media/galaxy3.png)

Now let’s sort through the above process:

1. The sum of the points of Alice and Bob playing cards is determined jointly by the both players.

2. The cards chosen and the card sums of each game are independent for each game, so historical game data cannot be used to make predictions about future games.

3. Alice and Bob can’t know each other’s card values in advance, so neither one has an advantage.

4. Alice and Bob can choose any card, so the point distribution is even.

5. Alice and Bob cannot interrupt the game;

6. Any third party can audit the game process, because all data is stored on the chain.

It can be seen from the above analysis that the random number algorithm of Galaxy Consensus satisfies the six properties mentioned above, and is a safe and efficient random number generation algorithm.


# Leader Selection

As described in Part 1, in the process of consensus, the nodes will form two large groups — the RNP (Random Number Proposer) group and the EL (Epoch Leader) group. The former is responsible for the generation of random numbers, while the latter is responsible for block production. One of the key problems for any consensus protocol is determining which individual node will be the block producer. This article will explore how the block producer is chosen from within the EL group (leader selection).

### I. The significance of rational leader selection

In Part 1 of this series, we explained that the two core issues to be addressed in any blockchain consensus protocol are Leader selection and Chain selection. Rational leader selection is of utmost importance to the [safety](https://en.wikipedia.org/wiki/Safety_property) and [liveness](https://en.wikipedia.org/wiki/Liveness) of a chain and is the cornerstone of a healthy consensus protocol (You can read more about safety and liveness in this excellent [blog article](https://blog.cosmos.network/understanding-the-basics-of-a-proof-of-stake-security-model-de3b3e160710) from the Interchain Foundation).

The proliferation of a chain is essentially the continuous connection of blocks, and it is block producers who package and propose new blocks. Block producers decide which transactions are written into the block and put on chain, and also determine the development direction of the chain through parent block selection. Under the conditions where a network consists of both good and malicious nodes, a good leader selection algorithm ensures that the honest nodes get the right to produce blocks and lead the development of the chain. Of course, since different consensus protocols make different security assumptions, the design of the leader selection algorithm varies between chains. Let’s explore some of the concepts and considerations significant to leader selection algorithms:

### Safety:

Let us first talk about the significance of the choice of the block producer to a chain’s safety. Safety refers to the property of a distributed computing system which ensures that ‘[nothing bad will happen](https://en.wikipedia.org/wiki/Safety_property).’ In the case of Bitcoin or other cryptocurrencies, this could refer to double spending or other cases of the wrong information going on chain.

### Security Assumptions by Protocol Type:

Different protocols can ensure safety under different security assumptions. Let’s take a look at some of the more well known protocols and their security assumptions:

**Proof of Work (PoW):** 50% or more honest participants:
PoW protocols use hash operations to select block producers, that is, the nodes repeatedly perform hash functions in order to find some random data to solve a problem. This is the process commonly referred to as mining. The answer to the problem is not predictable, and no node has any advantage in solving the problem, it is purely a computational competition. Under this type of system, as long as more than 50% of the work is from honest nodes, the safety of the chain is ensured.

**Byzantine Fault Tolerant (BFT) protocols:** 2/3 or more honest participants:
BFT-like protocols usually adopts the turn taking or probability selection for leader selection. No matter which method is adopted, the consensus protocol must ensure that the majority of block production rights go to honest nodes, and also require that the participating nodes vote on the proposed blocks. Only the block that has won more than 2/3 of the votes is the final valid block, thus ensuring the safety of the chain.

**Proof of Stake (PoS): **more than 50% honest participants:
PoS protocols randomly select the block producers according to their proportion of stake in the system. The key to the security of this type of system is a secure source of randomness which ensures that honest participants are chosen to lead the development of the chain, thereby ensuring the safety of the chain.

The above introduces the designs of common consensus protocols with different security assumptions. Of course there are many variations on the above described protocols which will not be discussed in detail here. It can be seen from the above that a rational leader selection algorithm is extremely important for the safety of the chain.

### Liveness:

Let us briefly discuss the significance of leader selection for the liveness of a chain. [Liveness](https://en.wikipedia.org/wiki/Liveness) refers to the ability of a chain to continuously process transactions without stalling, and the assurance that valid transactions will be confirmed after some period of time. Block producers are responsible for the propagation of the chain, and are responsible for chain liveness. In general, to ensure chain liveness, two problems need to be solved:

*First, the liveness of the block producers must be guaranteed.* Block producers must actively participate in the consensus process, not be offline or dormant in such a way which influences the propagation of the chain.

*Second, data consistency between nodes must be guaranteed.* honest nodes must be able to receive valid legal transactions, and honestly package them into the block for confirmation.

Together with the above discussion of safety, the chain’s liveness can be guaranteed. The liveness of the block producer is guaranteed by the leader selection algorithm. Leader selection is a generalized concept, and does not necessarily refer to any specific selection algorithm, but must considered in the overall design.

### II. Important considerations for a leader selection algorithm

The importance of the leader selection algorithm is introduced above. Which questions should be considered when designing a leaser selection algorithm, which properties are the measure for evaluating the quality of a leader selection algorithm?

1. **Fair 
**The block production rights are distributed according to the qualifications of the consensus nodes. For example, the higher the computation power in PoW, the greater the chance of obtaining the right to be the block producer, and the greater the amount of stake held in PoS, the greater the chance of obtaining the block production right. The concept is very natural and reasonable, but not easy to put into practice. To achieve true fairness, we need to avoid many problems. Let us illustrate with an example: Suppose A and B are two block producers. Which node gets the block production right is decided by rolling dice. If an odd number is rolled, then A obtains the block production right. For if an even number is rolled, then B obtains the block production right. Under fair conditions, the dice are thrown by “God”, and A and B’s chances are each 50%. If, however, A gets the right to roll the dice, then it is no longer fair. He can experiment and even change the numbers on the dice in order to get the block production rights, and then can decide to develop the chain in any way he/she wishes.

1. **Verifiable: 
**The legality of the right to block should be publicly verifiable. For example, the hash value of the block header in PoW can be easily verified by the whole network. This property is an obvious and inevitable requirement. As a decentralized system, the blockchain must be accepted and approved of by the whole network. The verification of valid blocks is one of the basic requirements. In addition to verifying the legitimacy of the transactions and the structure of the block, the validity of the block producer must also be able to be verified, so any leader selection algorithm must ensure that the ownership of the block right can be verified.

1. **Anonymity: **The block producer should be able to participate anonymously. This property is not an inevitable requirement. It is proposed because anonymity can solve security risks that may arise in consensus, such as corrosion attacks. Specifically, if the block producer is known by the whole network, then the malicious nodes may corrupt it through bribery, and turn the original honest node into a malicious node. The block producer may even be susceptible to cyber attacks, and be knocked offline in order to benefit malicious nodes. Therefore, achieving anonymity is also a problem to be considered when developing a consensus protocol. Many projects (such as Dfinity, Algorand) use the [VRF algorithm](https://en.wikipedia.org/wiki/Verifiable_random_function) to achieve anonymity, but VRF also has its own flaws and drawbacks. There are some proposals (such as Ouroboros Crypsinous) which use zero-knowledge proofs for anonymous consensus, but have not yet been implemented.

### III. Common leader selection algorithms

After explaining the importance of leader selection and discussing the important design considerations for a leader selection algorithm, we will now describe three popular leader selection algorithms.

1. Hash rate competition

A competition based on hashing power is the earliest block selection algorithm used in the context of blockchains. The most typical one is the Bitcoin system, which is a relatively simple and crude, although effective method. After the consensus nodes bundle the transactions, the hash value of the block header is repeatedly calculated by continuously adjusting the random number in the block header. When the hash value is smaller than the difficulty value required by the current block, a valid block that meets the requirement is formed, and then broadcast to the network. The first node to do this then becomes a valid block producer, that is in short, the complete mining process. The advantage of this approach is that it is fair to all participating nodes. No node will gain an advantage in computing hashes. As long as half of the overall computing power is safe, then the chain is safe. At the same time, this method may have multiple legal blocks and legal block producers a the same block height, so there will be short term forks, which is why the Bitcoin system needs to wait for confirmation time. At present, this kind of leader selection algorithm has the highest degree of decentralization amongst all consensus protocols. Of course, with the development of technology and the deepening of research, mining has gradually developed from the initial CPU mining to GPU and ASIC mining. Computing power is growing rapidly, and many projects have designed new consensus protocols for resisting chip mining by adding storage requirements, such as Zcash’s Equihash.

2. Verifiable Random Function (VRF)

The VRF algorithm is used for the leader selection algorithm to solve the issue of anonymity. The specific method is to first set a reasonable threshold value. The nodes then user their own private keys to perform a calculation using some random data, and if the result of the calculation is less than the threshold, then that node wins the right to be the legal block producer. In this process, the private key calculations can only be performed by the node itself, which ensures that other nodes cannot know who earned the right to block production, and the calculation result can be publicly verified, ensuring that the validity of the block production rights can be verified, thus forming the entire leader selection process.

Obviously, this method is probabilistic. If you want to have as many legal block producers as possible at a certain block height, you need to increase the threshold value as much as possible. Otherwise, if you want to have as few legal block producers as possible, then you should to reduce the threshold value as much as possible.

This means the setting of the threshold value can have a great impact on the greater system as a whole, and it is very difficult to achieve an optimal value. If the threshold is high, then it could lead to a large number of legal block producers at some block height, leading to many forks. If the threshold value is low, there may not be any legal block producer at all. Therefore, although the VRF algorithm solves the anonymity problem, it has a number of drawbacks as well.

3. Follow-the-satoshi

Follow-the-satoshi is a common leader selection algorithm in proof of stake protocols. This method relies on generating a random number, and then using that number to pick a random token from amongst all the staked tokens. Whoever is the owner of that token is selected as the valid block producer. The challenge of this approach lies in how to find a secure random source to generate true random numbers. Cardano currently uses the follow-the-satoshi method for the selection of block producers.

The generation of the random numbers uses multiple cryptography techniques such as multi-party computation and threshold secret sharing to ensure the security of the random source. The anonymity of leader selection has not yet been implemented. However, in terms of random number generation, another way is to use the hash value of a certain piece of historical data on the chain, which the approach taken by Algorand, and the hash value of the previous block data and the current block height is used as the hash value. A random number such as that is a good pseudo-random source, but there is still a risk of it being deliberately controlled. To learn more about random number generation, you can refer to [Part 2](https://medium.com/wanchain-foundation/wanchain-proof-of-stake-consensus-technical-deep-dive-pt-2-9d53d8217fda) of this series.

### IV. Galaxy ULS (Unique Leader Selection) algorithm

The Wanchain Galaxy Consensus’s leader selection algorithm termed ULS, or Unique Leader Selection algorithm. It was designed from the ground up to consider fairness, verifiability and anonymity, and employs a variety of cryptographic methods such as secret sharing and zero-knowledge proofs to realize the anonymous selection of a single unique valid block producer in a fixed time window. The algorithm was also designed to reduce the probability of forks and improve the efficiency of consensus. Below we will introduce the overall principle of the Galaxy Consensus’s ULS algorithm.

1. EL group selection
The EL group is the main body for running the ULS algorithm. Let’s start with the source of the EL group. There is a brief introduction of this in Part 1 of this article series, and we will here give a detailed explanation. In a PoS protocol, the right to speak is determined by the amount of stake held, and we implement this in the selection process of the EL group. Based on the current stake in the Wanchain consensus smart contract, the stake value of each node and its stake ratio can be calculated. Using the random number provided by the Random Beacon, the follow-the-stake-ratio algorithm is run, similar to the follow-the-satoshi process. Each node is assigned a certain breadth of time proportional to its stake, and then the random number is used to decide a specific time. Whomever’s breadth of time in which the time is chosen, the owner of that breadth of time is then selected to be in the EL group. Each round is an independent selection, meaning that a node may be selected multiple times, so the final EL group is a multiset (nodes may be chosen more than once within one EL group). The selected EL group will then be responsible for running the ULS algorithm.

![Epoch Leader Selection](media/galaxy4.png)*Epoch Leader Selection*

2. Secret Message Array generation
After the EL group is selected, it needs to communicate on chain. The process is to generate a secret message sequence inside the group for subsequent assignment of block production rights, which is a key step for us to achieve anonymity. In order to ensure that the secret message sequence is not controlled by some malicious nodes, we split the process into two phases, SMA1 and SMA2. In the SMA1 phase, each node in the group selects a random number, encrypts it with its own public key, and sends it to the chain as a commitment (CM) for the random number selection, ensuring that the random number selected by any node cannot be changed in subsequent stages. In the SMA2 phase, each node in the constellation sends its own chosen random number to the chain with the public key of all nodes (including itself), and provides a [DLEQ-Proof (discrete log equivalence proof)](https://blog.cloudflare.com/privacy-pass-the-math/), which is used in the SMA1 phase. The key-encrypted data ensures that the random number has not changed, and the DLEQ proof ensures that all public keys are encrypted with the same random number. After this phase is completed, all EL group nodes can all decrypt the data themselves and get a random data sequence, which is our secret message sequence, and are then ready to run the leader selection algorithm.

![](media/galaxy5.png)

3. EL group sorting
After the secret message sequence is generated, the random number is updated, and the newly generated random number is used as a seed to sort the EL group nodes. A hash operation is performed on the group node’s public keys and the random number, and the nodes are sorted in ascending order based on the operation result. This result will be used for the allocation of the order of subsequent block production rights. Obviously, the sorting is based on the new random number after the secret message sequence, and no node can affect it, the sorting is completely random.

![EL Node Group Sorting](media/galaxy6.png)*EL Node Group Sorting*

4. Slot leader selection
After the above three tasks are completed, the distribution of the block production rights can be performed for the EL group nodes. In the previous article, we said that a group of EL nodes is responsible for the generation of blocks within an epoch. How then is the block producer of each slot in the epoch determined? First, the current random number and the epoch number and the slot number are hashed, and the [modulus](https://en.wikipedia.org/wiki/Modulo_operation) of the number of EL group nodes is used to pick the slot leader. For example, if the hash value is 2019, the number of EL group nodes is 50, the modulus result will be 19, so then the EL node with the number 19 in the order from the previous sorting step is selected as the valid block producer (slot leader). This selection process is carried out with equal probability for all members of the EL group. Combined with the stake rate which is used when the EL group nodes are selected (remember, the EL group is a multiset meaning a single node may appear in it more than once), it ensures that the choice of the block producer is made in accordance with the ratio of stake held by consensus participants. The valid block producer must provide proof of its validity when proposing a block, and this proof must be publicly verifiable in order to guarantee its validity. The secret message array used in the selection of the slot leader is shared only within the EL group, other nodes have no knowledge of it, which guarantees the anonymity of the selection process. It can thus be seen that the ULS algorithm is a design that fully considers fairness, verifiability and anonymity, and will play an important positive role in ensuring the safety and liveness of the chain.

![Secret Message Array](media/galaxy7.png)

# Delegation 

### I. Delegation Mechanism  

There are already many PoS consensus mechanisms in the blockchain industry. They have been proposed by rigorous and meticulous academics and industry experts with rich experience, but they are generally lacking in practicality.

The following points are of particular concern:

**High participation threshold
**While PoS consensus protocols do not require the high computing power and investment in expensive mining hardware associated with PoW protocols, there are sill requirements for certain level of computing power and network bandwidth in order to for participants to successfully take part in consensus. This means that PoS participants still need to invest a certain amount in getting their nodes set up in running. Cost will vary depending on whether the node operators use AWS or get set up on bare metal, but the fact remains that there are some costs of getting set up and running. This, combined with the PoS principal that participants are rewarded in proportion to the amount of stake they hold, establishes a certain threshold for participation. Participants will only be able to profitably join in consensus when the protocol rewards are higher than their operation costs. This establishes a certain minimum threshold which will shut out a certain number of participants. This is a not a part of the protocol’s theoretical design, but it is still a practical concern.

**Centralization risk**
Due to the high participation threshold, only larger stake holders can profitably participate in the PoS consensus process to obtain rewards. The consensus gains obtained will increase the gap between consensus participants and non-participants, and thus will lead to a vicious circle of “the rich get richer and the poor get poorer”, which may eventually lead to increased centralization.

**Risk of violating basic security assumptions**
The security foundation of almost all PoS consensus mechanisms is the honest majority assumption, that is, honest nodes make up the majority of participants in the protocol. While the honest majority assumption may be true for all stakeholders in the network taken as a group, it may not be true for all stakeholders who can pass the participation threshold. If there is a very high participation threshold which prohibits many stakeholders from joining, then participants will be chosen from a much smaller pool of stakeholders which might not represent the entire network. This is essentially a sampling problem. The higher the threshold, the smaller the sample, and the less likely the set of participants reflects the nature of all stakeholders in the network. The issue is therefore how to design a mechanism which can reduce the participation threshold in order to absorb as much stake from as many participants as possible.

### II. The significance of Galaxy Consensus’s delegation mechanism

We have from the start considered practicality when it comes to the design of Galaxy Consensus. By practicality we refer not only to reducing the computational and storage requirements needed to participate in the consensus process, but more importantly, to ensuring that stake holders can smoothly participate throughout the process. Galaxy Consensus has a robust delegation mechanism in which nodes with larger amounts of stake can participate directly in the consensus process, while smaller WAN holders can join through the delegation mechanism. In theory, any WAN holder can join the consensus process, which is in the spirit of our open and inclusive PoS design. Under this scheme, more WAN will join the protocol, making the entire network more secure and robust. Therefore, the delegation mechanism reduces the threshold for PoS consensus participation, improving the practicality of Galaxy Consensus, and has several advantages*** ***compared with other PoS consensus protocols.

### III. The theoretical basis of Galaxy Consensus’s delegation mechanism — proxy signatures

A proxy signature is a special signature algorithm in cryptography that enables an individual, the Original Signer, to delegate his or her right to sign a message to another individual, the Proxy Signer. The Proxy Signer can calculate a delegate signature, and any individual with the Original Signer’s public key can verify the validity of the signature. Strictly speaking, the proxy signature algorithm is a collection of multiple algorithms,

***PS = (G, K, S, V, (D,P), PS, PV)***

where ***G, K, S, V*** make up a standard digital signature algorithm (such as ECDSA), **D, P** are algorithms for delegating and accepting delegations, **PS** is the proxy signature generation algorithm, and **PV** is the proxy signature verification algorithm.

![*Proxy Signature Algorithm*](media/galaxy8.png)**Proxy Signature Algorithm**

### IV. Galaxy Consensus’s Delegation Mechanism Process

The delegation mechanism of Galaxy Consensus was designed by the Wanchain research team as a universal, secure, and efficient delegation mechanism. The mechanism is based on the Triple ECDSA Proxy Signature algorithm, which, combined with smart contracts, implements a complete delegation mechanism. The mechanism enables any WAN holder to join the Galaxy Consensus, contribute to network security, and gain protocol rewards.

Suppose Alice is a normal WAN holder with public-private key pair ***(pkᵢ, skᵢ)***,and Bob is a galaxy consensus proxy node with public-private key pair ***(pkⱼ, skⱼ)***. Proxy_SC is a special smart contract used to verify and store data in the delegation process. Alice wants to delegate her rights to Bob to participate in Galaxy Consensus on her behalf. The detailed process is as follows:

**Step 1: **Alice locally enters her private key ***skᵢ* **and Bob’s public key ***pkⱼ*** into the triple ECDSA algorithm to generate a delegation certificate:

***cert =（pkᵢ,pkⱼ,ω,(R,s)）***

**Step 2:** Alice constructs a transaction, sends the delegation certificate to Proxy_SC, and sends her WAN to be locked in Proxy_SC.

**Step 3:** Proxy_SC verifies the validity of the proxy certificate issued by Alice, and generates the proxy public key ***pkp*** and the delegation certificate to be stored in the contract.

**Step 4:** Bob parses the certificate stored in Proxy_SC and calculates the proxy private key ***skp*** by using its own private key ***skⱼ***.

**Step 5: **The proxy public key ***pkp*** participates in the galaxy consensus as an independent identity, and Bob completes the consensus process by using the proxy private key ***skp ***and receives the consensus reward.

**Step 6:** Consensus rewards are distributed between Alice and Bob according to the specified rate in the smart contract.

**Step 7:** After the delegation period ends, Proxy_SC will return the entrusted funds to Alice’s account.

![](media/galaxy9.png)

**5. Advantages of the galaxy consensus delegation mechanism**

**Universality**
The mechanism uses the ECDSA signature algorithm in standard signatures, stake delegation, and proxy signatures. This algorithm is also widely used in the blockchain field. It is fully compatible with existing blockchain architectures. The verification logic for participants is completely consistent for both directly registering to join the consensus mechanism and for joining through the delegation mechanism.

**Non-interactive**
The process of delegation is non-interactive, so there is no need to establish a secure communication channel between the Original Signer and the Proxy Signer. The delegation is completed completely through the on chain transactions leading to a more efficient consensus process.

**Secure**
Some existing delegation mechanisms require the delegating party to transfer funds into the proxy node’s account, and the proxy node then directly participates in consensus and manually distributes consensus rewards. This method is centralized and trust based. It relies entirely on the honesty of the proxy node. Our delegation mechanism is implemented based entirely on cryptographic algorithms. The stake of the WAN holder is locked in a smart contract, not held by the proxy node. The proxy node only obtains the right of the WAN holder to participate in consensus, and does not have any control over the staked funds, so users are fully protected.

**Open and Transparent
**Through our mechanism, the delegation process and the data of the nodes participating in the consensus process are all stored in the chain, and all the data is transparent. This both promotes proxy nodes to behave non-maliciously, while it also makes it possible for WAN holders to analyze the activities of proxy nodes and select an appropriate node based on their history.



# Economic Incentives

### I. The significance of economic incentives

Economic incentives are one of the core elements of Galaxy Consensus. A rational economic incentive mechanism is the fundamental force which suppresses malicious behavior and ensures that consensus nodes operate honestly.

*In a narrow sense, the economic incentive mechanism is a basic guarantee for maintaining node operation, ensuring the chain’s safety and liveness.*

We know that for blockchain systems, consensus nodes are responsible for packaging transactions, generating blocks, and shouldering the heavy responsibility of chain development. The active and honest participation of consensus nodes is key to ensuring chain safety and liveness. In our consensus design, we have payed close attention to a variety of technical elements, such as leader selection and random number production, which we have explored in earlier articles of this series. The core purpose of each of these designs is to establish a healthy and efficient consensus system. However, after covering all of these mostly technical design elements, we now come to an element which lays in large part outside of the technical realm. That is, why should nodes participate in our protocol at all, how can a rational economic incentives mechanism which promotes the honest participation of nodes be designed? At a basic level, the mechanism should reward nodes for participating in the process of running the consensus protocol. The reward must cover both the cost of maintaining and running the node, and must also provide an additional incentive over the costs to ensure that nodes are motivated to continue their operation. A good economic incentive mechanism encourages nodes to behave honestly by maximizing rewards for honest nodes, while at the same time discouraging malicious behavior. Such an incentives mechanism creates the basic economic environment for the protocol to operate healthily, and ensures the smooth development of the entire system.

*Broadly speaking, the economic incentive mechanism is the foundation of the blockchain’s ecosystem and ensures the smooth circulation of value.*

Blockchain technology is currently pushing the Internet forward from the Internet of information to the Internet of value. A decentralized system of value was established with the emergence of Bitcoin which removes the definition of value from centralized control to that of a decentralized consensus mechanism.

Only value which can freely circulate is meaningful. The basis for value of the Bitcoin network is the circulation of value. Nodes in the network are rewarding for their bookkeeping work, and their bookkeeping also allows for the circulation of value, thus forming a closed loop. It can be seen then that economic incentives are the driving force of blockchain ecosystems. Economic incentives drive the operation of consensus, consensus ensures the circulation of value, circulation allows for the value to have meaning, and the meaningful value forms the basis of the economic incentives. Economic incentives are therefore the ignition system which play a fundamental role in making the ‘engine’ of the blockchain run.

### II. Several basic issues to be considered in economic incentives

We know that a good economic incentive mechanism encourages honesty and curbs malicious behavior. What basic problems must be considered in incentives design? What exact behaviors should be rewarded or discouraged. 

**> Behaviors which must be incentivized by consensus type:**

In systems such as Bitcoin and Ethereum which use Proof of Work (PoW), only miners which perform hashing calculations contribute to consensus. These miners give themselves a certain amount of reward in each of their own proposed blocks. Of course, there are some exceptions. In the development of Ethereum’s consensus, in order to reward those who proposed valid blocks but were not chosen as block producers, the concept of an “uncle block” was put forth. Under this concept, a small reward is given to indicate the recognition of these node’s work. For a detailed explanation, interested readers can refer to [Vitalik’s blog](https://blog.ethereum.org/2014/07/11/toward-a-12-second-block-time/).

In systems such as Ouroboros and Dfinity which use Proof of Stake (PoS), we must incentivize not only the nodes which propose blocks, but also the nodes which contribute to the generation of randomness. As we have discussed in our [previous article](https://medium.com/p/9d53d8217fda), entropy (randomness) in a PoS protocol is essential for the security of the protocol. The entropy in the protocol must come from a trusted random source, so there needs to be a set of nodes dedicated to generating random numbers. The work of these nodes is an indispensable part of the consensus mechanism, so these nodes must also of course be rewarded. So it can be seen that under this type of consensus protocol, two actors must be rewarded, block producers and random number generators.

In systems such as EOS and Cosmos which use the Byzantine Fault Tolerance (BFT) consensus protocol, the nodes participating in consensus need to vote for candidate blocks. Only the blocks which have obtained a certain percentage of votes will be validated. In such consensus agreements, the subjects which must be rewarded are the nodes responsible for voting.

**> Reward source which ensures continuity:**

There are two types of reward sources. One is similar to Bitcoin. The total amount of rewards is set at the beginning, and then released in a continually decreasing schedule with a fixed amount released to miners for each block. A similar reward source is often seen in PoS protocols. Under these protocols, a certain amount of initial funds are reserved to reward consensus participants, and these funds are also released in a continually decreasing schedule.

Both of the above mentioned reward sources don’t include any additional issuance of tokens through inflation, and we won’t include any discussion of systems which include inflation. Additional inflation will naturally dilute the value of any rewards issued in the system. While our system does not include inflation for this reason. This ensures that the value in the system remains stable.

Since the fixed reward will be naturally reduced over time, the question arises, will node operators begin to lose interest in participation as the rewards decrease? How can we ensure that rewards remain sufficient to maintain the system over time? This problem must be considered carefully in the design. In addition to adjusting the parameters such as the percentage of reduction of reward and the periods at which the reduction happens, the most important feature is that in addition to the fixed incentives, node operators also receive transaction fees for their work. These transaction fees are paid by the transaction initiator for the consensus node’s bookkeeping work. With the improvement of the ecosystem, the increase of transactions, and the increase of value, this part of the compensation will gradually become the main reward and the source of economic incentives in the system.

**> Ensuring the fairness of rewards:**

Ensuring the fairness of rewards is a very broad concept. We touched on the basic principles of economic incentives in our Galaxy Consensus yellow paper. The first principle is that rewards should be equivalent to the contributions. For example, if a node participates in consensus, but does not do any work after registration — does not work to package transactions for block production and does not participate in random number generation — then this type of node will be considered ‘lazy,’ and should not be rewarded. Therefore, there must be criteria for judging when to reward, and there should be an assessment of the behavior of the nodes participating in consensus.

For this purpose we have introduced the concept of an ‘activeness’ coefficient in Galaxy Consensus. Under this concept, nodes which are not actively participating in consensus will lose some or all of their rewards. This ensures the fairness of the mechanism, laying the foundation for a rational and benign competitive environment which allows for the healthy operation of the consensus protocol.

**> Considering the delegation mechanism:**

In our [previous article](https://medium.com/wanchain-foundation/wanchain-galaxy-consensus-proof-of-stake-technical-deep-dive-pt-4-5e5e51fa4637), we outlined in detail Galaxy Consensus’s robust delegation mechanism. In the article we emphasized that the mechanism reduces the threshold for participation in PoS consensus, and is of great importance to the practicality and security of the entire consensus. So how should economic incentives for the delegation mechanism be designed?

We start from considering the significance of the delegation mechanism when considering this problem. First of all, it is to lower the threshold for participation in consensus. That is, to give holders of smaller amounts of tokens an opportunity to participate in consensus. This is done by allowed them to designate a proxy to operate in the consensus protocol on their behalf. Then they should provide the proxy agent with a processing fee. We therefore allow the proxy agent to set their own commission rate, so that they can receive a part of the consensus reward from the tokens delegated to them in compensation for their work.

We must also consider another issue. If the proxy agent is allowed to accept a large amount of delegations, although the agent may hold a significant amount of stake themselves, their power within the consensus protocol is very large. For example, if the proxy node has only 100,000 of their own tokens staked, but accepts 1 million tokens in delegations, than that node represents 1.1 million worth of staked tokens in the protocol. This means that while the node has a relatively small amount of its own stake in the system, they represent an much larger amount of stake in the protocol due to the delegations they have received. This naturally brings about the issue of the proxy agent potentially behaving maliciously in order to benefit itself, without fear of harming their relatively small stake in the protocol. We therefore set a delegation ratio limit for the acceptable amount of delegations a proxy node is allowed to receive. For example, if we set a 1:1 delegation ratio, then if a proxy node has 100,000 of its own stake, it can only receive up to 100,000 in delegated stake, for a total of 200,000. If the ratio is 1:5, then for 100,000 of its own stake, a node can then receive up to 500,000 in delegated stake for a total of 600,000. For delegations over the ratio limit, the node will no longer receive additional rewards. When setting this limit, we need to balance both the economic incentives and also the security implications of this limit.

### III. Common economic incentives

In general, there are two categories of economic incentives, positive and negative.

**Positive incentives:** Simply put, participants will be rewarded for completing work required by the protocol. For example, in Galaxy Consensus, participants must complete a number of actions defined by the protocol, such as random number generation, packaging transactions, and proposing valid blocks. We therefore issue rewards as positive incentives for participants which complete these actions.

**Negative incentives: **Negative incentives aim to suppress any malicious behavior aimed at damaging the protocol. There are two common negative incentives: slashing, and reduction of rewards. Slashing requires a system of supervision, in which evidence of malicious behavior must be submitted, and then the node’s stake is slashed based on that evidence. One of the difficult points here is in defining how to identify malicious behavior. Some well know examples of malicious behavior include double signing and long ranged attacks. As for reduction of rewards, essentially this is simply applying the principle of maximizing the rewards for those nodes which faithfully follow protocol rules. For example, if the nodes participating in random number generation try disrupting this process by submitting inconsistent information at different stages, then when the rewards are distributed, these nodes will not be rewarded, thus suppressing this type of malicious behavior.

### IV. Galaxy Consensus’s incentives model

After introducing the above design considerations, we will now take a close look at the incentives model implemented in Galaxy Consensus. The reward source of Galaxy Consensus consists of 10% of the total WAN issuance provided by the Wanchain Foundation, which is 21 million WAN. This part of the funds will be dispersed in a series of decreasing stages. In addition to this fixed reward, transaction costs will also be a part of the reward received by nodes. The reward is not distributed per block, but rather after each epoch is settled. The transaction fees will be shared between Random Number Proposers (RNP), and Epoch Leaders (EL) in order to ensure that all participants are rewarded fairly. We believe that the role and contributions of RNP and EL nodes are equally important in the consensus operation, so in each epoch, the reward will be evenly distributed between random number proposers and epoch leaders. That is, if each node runs honestly and completes its work, then the benefits will be the same.

**Economic incentives for [random number proposers](https://medium.com/p/9d53d8217fda)**

Earlier we emphasized the important role of random numbers in consensus protocols, and also stated that nodes must be incentivized for their work in random number generation. For for random number proposers, it is relatively easy to determine whether they have done their work honestly. First, let’s look at the work that nodes must do to participate in random number generation:

>Submit commitments in DKG1 phase.
>Submit encrypted data and proof in DKG2 phase.
>Submit signature fragments in the SIGN phase.

As long as the nodes participating in random number generation complete each of these steps, their work is done and they will receive their rewards. If they miss or incorrectly complete any of these steps, they will not receive any reward.

**Economic incentives for [block producers](https://medium.com/p/3a210891b2ae)**

Lets take a look at the work required of block producers:

>Submit the commitment in the SMA1 phase.
>Submit the encrypted data and proof in the SMA2 phase. 
>Complete the secret information sequence sharing.
>Propose the block in the slot package transaction that it is responsible for.

These four tasks can be divided into two parts according to the work content. The first two items concern the secret message array, while the latter items concern block generation. Therefore, the overall reward of the block producers will be split into two parts. One part is used as the reward for the secret message array generation, and another part is used to reward block production. Similar to random number generation, the two stages of secret message array generation are a complete process, which requires all steps to be completed by the node for it to be considered completed. Therefore, the block producer can only get this part of the reward if it is correctly completed. Additionally, an activeness coefficient will be taken into account in order to measure the activeness of the participants. The higher the group activity, the larger the rewards received by the group.

**Delegation Rewards**
As mentioned above, in the delegation mechanism, the validator will take part of the reward according to the delegation fee set for compensation, and the remaining part of the reward will be received by the delegator. If the amount delegated goes about the delegation limit, then the reward received by both will be zero.

