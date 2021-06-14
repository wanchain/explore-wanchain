# Chapter 3: Wanchain 5.0 Cryptographic Foundation

![](https://miro.medium.com/max/2732/1*AOudZU59x8B3qDyhUqjY2w.jpeg)


## Introduction


There are two fundamental problems to be solved in any cross-chain solution, one — how to lock and manage cross-chain assets, and two — how to verify cross-chain information. Wanchain 5.0 solves these two problems in a decentralized way using cryptographic techniques. In this article, we will introduce Wanchain 5.0’s solutions to these two problems and their advantages compared to other existing solutions.

## Management of Locked Cross-chain Assets


### Overview of Options for Managing Locked Cross-chain Assets

There are three commonly used methods for locking cross-chain assets, protocol-based methods, multi-signature based methods, and Multiparty Computation with Threshold Signatures Scheme (MPC / TSS) based methods. Wanchain makes use of a MPC / TSS based method.

Compared to other methods, it has the following advantages:

*   **Universal —** It is applicable for any blockchain system without changing underlying mechanisms
*   **Efficient —** Only one valid signature is needed to control the locked account, which reduces storage and computation
*   **Flexible —** it allows any number of nodes to control the locked account and is adjustable to suit different needs

Wanchain applies different TSS (threshold signature schemes) according to the technical structures of blockchain systems. Specially, for blockchain systems that do not support smart contracts (such as Bitcoin), we use an ECDSA TSS scheme. For blockchain systems that support smart contracts (such as Ethereum, EOS), we use a Schnorr based TSS scheme. Wanchain 5.0 includes major upgrades to our previous TSS schemes, which ensures the security and decentralization of the whole system.

### Wanchain 5.0’s Improved Threshold-optimal ECDSA TSS

We will first explain the concept of “threshold optimal”. Generally, in a `(t,n)` TSS scheme, there is a total number of `n`participants, of which `t` participants are required to generate a valid signature. “Threshold optimal” indicates that `t` can range from 1 to n, i.e. `t∈[1,n]`. The ECDSA TSS scheme most commonly used by blockchain projects is from tjepaper “Robust Threshold DSS Signatures” published in 1996. This scheme is not threshold-optimal, for `t∈[1,(n+1)/2]`. Because in this scheme, the secret key is divided into secret shares by Shamir secret sharing. When performing the MPC multiplication operation in the signing process, degree of the polynomial which shares the multiplication result will increase to `2t-2`. The formulae are as follows:

![](https://miro.medium.com/max/860/0*Q_m-Z8HajOtU7rv5.png)

`s` denotes the secret key, `f(x)` denotes the polynomial used to share `s`, `r` denotes the nonce in ECDSA scheme, `g(x)` denotes the polynomial used to share `r`. In the signing process, shares of `s` multiplicate with shares of `r`. Then `F(x)` is the polynomial that shares `sr`, of which the degree is `2t-2`. So in order to recover `sr`, the least number of participants is `2t-1`, which should be less than `n`:

![](https://miro.medium.com/max/266/0*MQfXglI17Ktsoc-k.png)

Then we know `t∈[1,(n+1)⁄2]`.

Wanchain 5.0 employs the latest research into ECDSA TSS schemes to improve our cross-chain solutions for Bitcoin. Our ECDSA TSS scheme is from the paper “Fast Multiparty Threshold ECDSA with Fast Trustless Setup” published in 2018, which uses homomorphic encryption and the MtA (Multiplication to addition) protocol to ensure the solution is threshold optimal. The property of threshold-optimal is vital to any cross-chain solution’s security and stability. We discuss this in two aspects:

*   When `t` is fixed, regular ECDSA TSS schemes require no less than `2t-1` participants working together to generate a valid signature. But for threshold-optimal ECDSA TSS scheme, only `t` participants are required. For example, assuming 5 participants are enough to reconstruct the private key. Then in regular ECDSA TSS schemes, in order to generate the valid signature in the way of MPC, the secret key has to be spread to at least 9 nodes. If the adversary succeeds in attacking 5 of the 9 nodes, then he is able to reconstruct the secret key and steal the assets in the locked account. But in threshold-optimal ECDSA TSS scheme, the secret key is spread to 5 nodes. The adversary has to attack all of the nodes successfully to steal the assets in the locked account. To make a summary, when `t` is fixed, the secret key has a wider spread in regular ECDSA TSS schemes than threshold-optimal ECDSA TSS scheme, which raises the risk to be attacked. So threshold-optimal ECDSA TSS scheme is more secure.
*   When `n` is fixed, in regular ECDSA TSS schemes `t∈[1,(n+1)⁄2]`, but in threshold-optimal ECDSA TSS scheme `t∈[1,n]`. So the range of `t` in threshold-optimal ECDSA TSS scheme is almost one time bigger than that in regular ECDSA TSS schemes. When `t=(n+1)/2`, the valid signature cannot be generated in regular ECDSA TSS schemes if one of the nodes is offline. But in threshold-optimal ECDSA TSS scheme, the valid signature can always be generated as long as the number of offline nodes is less than `(n+1)/2`. So threshold-optimal ECDSA TSS scheme has the property of fault-tolerance and is more stable.

### Improve Shamir secret sharing to Feldman verifiable secret sharing

Wanchain applies Schnorr TSS scheme in blockchain systems that support smart contract. Compared to ECDSA TSS scheme, Schnorr TSS scheme has less computation consumption and fewer interaction rounds, which improves the efficiency of managing locked account. Wanchain 5.0 opens all the Storeman nodes to community, so a precise slashing mechanism is needed to punish the malicious nodes to ensure the security of cross-chain process. The basis for such a slashing mechanism is a method to verify the validity of data sent during the TSS signing process. So we improve the original Schnorr TSS scheme by replacing the Shamir secret sharing with Feldman verifiable secret sharing. After the improvement, any node can verify the validity of its data received from other nodes. One the data is invalid, the node can upload it to a special smart contract, which will verify the data and punish the corresponding sender.

## Solution To Verifying The Cross-chain Information

There are two ways to verify cross-chain information — proof-based methods and consensus-based methods. In proof-based methods, the sender of cross-chain information has to provide an extra proof to prove the validity of the related cross-chain information. In consensus-based methods, a group of nodes consensus on the cross-chain information, of which the result determines the validity of the cross-chain information. Wanchain 5.0 adopts a consensus-based method to verify the cross-chain information. Based on the idea of “signature is consensus”, we combine the verification of cross-chain information with the management of locked account. The Storeman node verifies the cross-chain transaction in the original chain locally, generates the corresponding signature share, and sends to the destination chain. Once the number of signature shares exceeds the threshold (such1/2, 2/3 ), it means that the Storeman nodes have reached consensus on that cross-chain transaction. At the same time, these signature shares are constructed into the complete signature, which triggers the cross-chain assets generation and release. Compared to the proof-based method, our solution is user-friendly because of the fact that users have to send only one single transaction, which reduces cost and time.


