# Universal Multichain Bridges with Shared Staking Assets

![](https://miro.medium.com/max/5102/1*W1WdD9HNlBtCqmX1qxqYgw.png)

## Background


Wanchain is a project focusing on bridging homogeneous and heterogeneous blockchains to allow assets to transfer across multiple ecosystems. Recently Wanchain released Wanchain 5.0 with a fully permissionless and decentralized crosschain mechanism to include the following advantages:

• Wanchain 5.0 achieves the first implementation of open storeman meaning that anyone can join as a permission-less storeman. Wanchain community members know that Wanchain uses storeman to connect two blockchains for asset transfer. Wanchain 5.0 is the first release that makes storeman fully decentralized and changes from storeman to open storeman. Technically this is achieved through open MPC. MPC is a core technology of Wanchain to decentralize the ownership of accounts through a group of nodes, each owning a portion of a private key. At least over two-thirds of the nodes need to sign a transaction with their respective key share in order to transfer funds from an account. The MPC method combined with staking and slashing effectively prevents collusion by the storeman nodes.

• The reward rate for open storeman is coupled with the reward rate of Wanchain validator’s proof of stake. This is to present staking all going to the node validator or all going to storeman. As far as we know, Wanchain is the first project to implement this coupling mechanism. It increases the stability of staking for both the block validator and the storeman validator.

*   Wanchain provides a holistic open source crosschain suite for the 5.0 release. The Wanchain crosschain mechanism, storeman agents, P2P discovery, wallet, and browser have all been redesigned and implemented to increase performance and improve user experience.

## Next Steps: Scaling Wanchain Crosschain Platform


With the release of permissionless and decentralized Wanchain 5.0, Wanchain has accomplished the basic infrastructure as laid down in Wanchain’s whitepaper. The next phase of Wanchain’s platform is to expand its crosschain capacity to support larger total crosschain values and scale up the crosschain bridges. The major problems for scaling crosschain bridges include the following:

**· Security issue**

Since Wanchain’s bridges are decentralized and permissionless, the security of the crosschain assets is safeguarded by assets staked by the Storeman nodes to ensure that there is no collusion among them and any wrongdoing by the bridge operators will be slashed with the stakes deposited for the bridges. As the number of bridges increases, the stakes needed to secure a bridge increases accordingly. Hence the limited amount of stakes to secure bridges hinder the crosschain transaction’s scalability.

**· Bridge capacity issue**

Bridge capacity describes how many crosschain assets can be transferred and secured for a bridge. Today, stakes to secure crosschain transactions are bridge-based, meaning that each bridge has its own stake and the total crosschain value (TCV) should not exceed the amount of assets staked for that bridge. Since TCV is a changeable value for each bridge while stakes are allocated and attached to individual bridges, it is very likely that some bridges might have overflow of staking assets while others might hit the maximum crosschain transaction cap and need to be halted until more assets are allocated. The disparity of bridge capacities will negatively impact the overall security of the crosschain ecosystem.

**· Multi-Bridge compatibility issues**

Wanchain has started to support multi-bridge crosschain operations. One type of transferred asset in a blockchain can come from various source blockchains. For example, btc@ethereum can come from btc@bitcoin or btc@wanchain. Hence, problems arise as how we can guarantee that btc transferred from both sources are equivalent. To ensure that assets from different bridges are equivalent, the smart contract logic should be the same and the bridges should be secured. Furthermore, the operators that carry out the transfer will also be the same group of nodes that run compatible crosschain codes.

To overcome the challenges mentioned above to improve scalability of the Wanchain crosschain platform, we introduce the Universal crosschain mechanism that allows a common pool of Storeman nodes to use shared staking funds to manage multi-chain bridges.

## Universal Crosschain Mechanism


**Universal Crosschain platform Overview**

Wanchain Universal Crosschain platform is depicted in Figure 1 with the following components: a) set client devices such as a handheld mobile device, a device having a web browser, or a desktop with applications; b) a cross-chain API gateway that is connected to client devices and various blockchains, bridges, and blockchain hubs; c) homogenous or heterogeneous blockchains; and d) universal cross-chain bridges that connect blockchains to provide native or cross-chain transactions. Cross-chain API gateways as shown in the diagram may be implemented with different technologies. For example, an API gateway may have an HTTP server as a front end that communicates with client devices. In another embodiment, the API gateway may have a peer-to-peer connection with a client device and receives messages from the clients. The API gateway may also implement a load balancing server to increase the scalability and reliability of the gateway. The backend of the API gateway connects to native blockchains, bridge links, or blockchain hubs. A native blockchain is a blockchain that supports single chains and protocols, such as bitcoin, Ethereum, quorum, EOS, tron, corda, ripple, and hyperledger. A blockchain hub is a blockchain that has functions to perform cross-chain operations to transfer and aggregate assets, data, and value across blockchains. Blockchains such as Wanchain, Polkadot, and Cosmos may be classified as blockchain hubs.

![](https://miro.medium.com/max/875/1*as3QLkBD-mRHmx9tjyvSAw.jpeg)

Figure 1 Overview of Universal Crosschain Platform

In this architectural diagram, a blockchain bridge is a connector that connects two homogeneous or heterogeneous blockchains to allow data, value, and assets to flow across blockchains. The Wanchain bridge solution is implemented via Storeman nodes. A Storeman mechanism is a component node that is used to listen to events on multiple blockchains and processes and relays the transaction to the corresponding blockchains. A storeman node may have multiple running programs to form a cluster and each shares part of the secret for unlocking the accounts that stage the cross-chain values. The storeman mechanism will support staking that allows users to lock a portion of their assets through a smart contract to fund the running node and receive a reward for the cross-chain transaction.

**Storeman Nodes**

Storeman node components can be shown in Figure 2. A cross-chain bridge or Storeman may have two or more ports connecting to corresponding blockchains. A port may contain executable codes such as smart contracts, chain code, or scripts that may be used to perform operations on a blockchain to which it is attached. The executable code then transfers the operation and data to the bridge for further processing through the services in the cross-chain bridge. These services may include a validation agent to validate a cross-chain transaction, a sync agent to synchronize data and states among bridges, and an event agent to listen to and process events. Storeman nodes also network with each other to form a multi-party computing (MPC) group to control a shared key to lock and unlock accounts on both source and target blockchains.

![](https://miro.medium.com/max/875/1*Ejd7Ch176cJXyVWQZH_M2g.jpeg)

Figure 2 The architectural components of a crosschain bridge

**Shared staking funds for Storeman nodes**

In a universal crosschain platform, accounts in the blockchains may fund a bridge by locking a certain amount of assets in the blockchains in return for a reward of cross-chain transaction fees. This may be done by implementing smart contracts on a blockchain for a staking function such as stake\_deposit as a function of blockchain\_id, account address, amount, Bridge\_id, duration, and signatures to fund a bridge. Here, blockchain\_id represents a blockchain where the account is located, the account is a blockchain EOA (external owned account) from which a fund will be withdrawn or locked to support a bridge to process cross-chain transactions, the amount is the amount of the asset that will be deposited, bridge\_id represents the bridge for which the fund will be deposited, the duration is the length of time when the asset will be locked in the account, and signature is a signed message from the account owner to enhance the authenticity of the staking request.

Once account owners deposit their assets to the bridges, they accumulate stakes for the bridge fund (Figure 3). A bridge fund is the aggregation of the assets and value deposited to bridges in a bridge group. A bridge stake is a total stake deposited to a particulate bridge. A stake and an asset do not need to have a 1-to-1 matching relationship. For example, a stake may be a function of asset value with modifiers such as length of deposit time and other promotional factors such as deposit time or even a random lucky number. These multi-bridge stakes form the basis for the selection of bridges for processing cross-chain transactions as well as the basis for rewards. In general, the larger the stake a bridge has, the more chance for it to be selected as a Storeman node. Similarly, the larger the stake an account has, the larger the portion of the reward that account will receive.

![](https://miro.medium.com/max/875/1*yws2NUxXRfDx7kGUSab90Q.jpeg)

Figure 3 Shared Bridge Stakes

One important change for a universal crosschain platform is that the staked funds are shared among bridges and hence are “need-based” and can be dynamically allocated to bridges that carry out the transfer of crosschain assets.

## Advantages of Universal Crosschain

When compared with the existing Storeman node solution that Wanchain has, the shared Storeman node mechanism has several advantages in security, crosschain transfer capability, and scalability as shown below:

**Much simple process of transferring tokens from chain to chain**

![](https://miro.medium.com/max/875/1*CcqRoICkQmnjoPuSuzPM4g.jpeg)

![](https://miro.medium.com/max/875/1*HhwN7p5q4VHA76VlQOz9aQ.jpeg)

Figure 4 Schematic diagram showing differences of crosschain transfer via regular storeman nodes (top) and shared storeman nodes (bottom)

Shared storeman group makes the asset management and information verification between different blockchains much easier and the process of transferring tokens from chain to chain simpler as shown below.

The diagram shows a scenario where there are three blockchains of Ethereum, EOS and Wanchain respectively. Each blockchain has transferred bitcoin marked as wanBTC. For the regular storeman node (top of diagram) mechanism, two storeman groups are created with storeman group 1 (SG1) for the Ethereum and Wanchain bridge and storeman group 2 (SG2) for the Wanchain and EOS bridge. The workflow of transferring wanBTC from the Ethereum blockchain to the EOS blockchain follows the steps below:

Step1: User burns his wanBTC on Ethereum;

Step2: SG1 receives this event and mints the same amount of wanBTC for the user on Wanchain;

Step3: User burns the received wanBTC on Wanchain;

Step4: SG2 receives this event and mints the same amount of wanBTC for the user on EOS;

In the above procedure, a total number of 4 transactions are required, including 1 transaction on Ethereum, 2 transactions on Wanchain, and 1 transaction on EOS. Among these 4 transactions, the user is required to send 2 transactions — 1 transaction on Ethereum and 1 transaction on Wanchain.

With the shared Storeman group (shared SG), the procedure is simplified as follows:

Step1: User burns his wanBTC on Ethereum;

Step2: shared SG receives this event and mints the same amount of wanBTC tokens on EOS;

In the above procedure, a total number of 2 transactions are required, including 1 transaction on Ethereum and 1 transaction on EOS. Among the 2 transactions, the user is required to send 1 transaction on Ethereum.

**Low cross-chain transaction fee for users**

From the above we know, using the shared storeman group, that the user is required to send only one transaction to transfer his tokens between two different chains with no direct bridges. Thus the cross-chain transaction fee is 50% lower than before.

**Low cost of building bridges**

![](https://miro.medium.com/max/875/0*Us20K2K9fjJtZtOA.png)

Figure 5 Comparison of resource consumption between regular and shared storeman groups

In Wanchain 5.0, the locked account is generated jointly by the members of the Storeman group, which is denoted as the KeyGen process. This process requires all the members to participate and is both time and computationally consuming. Specifically, the total runtime and computation resource consumption grows linearly as the number of bridges increases. Using the shared Storeman group, only one KeyGen process is required, for the locked account is shared by the bridges. Thus, the total runtime and computation resource consumption remains constant as the number of bridges increases. Assuming the resource consumption in building one direct bridge is C, then the relationship of the total resource consumption and the number of building bridges is shown in Figure 5 above. Per this graph, the resource consumption for a regular storeman group increases in proportion to the number of bridges while the consumption for a shared storeman group remains constant.

**Better security**

![](https://miro.medium.com/max/875/1*G3-Ny1rmnYzcJodKBrB2bg.jpeg)

Figure 6 Difference of regular storeman group and shared storeman group for security consideration

Compared to separating the Storeman nodes into different groups, a single Storeman group with more members offers better security. We show this fact through a simple example.

![](https://miro.medium.com/max/875/1*Ho8_l843-pwbqZY9g5QZ5A.png)

Figure 7 Relationship of overall security of storeman groups versus affecting parameters

![](https://miro.medium.com/max/875/1*W5YEfUAlPw5qakIhhwDJbg.png)

Figure 8 Security computation for p=0.3 and TN=100

![](https://miro.medium.com/max/875/1*f0wLU9XkM-JT58l8_WeaUw.png)

Figure 9 Security computation for p=0.2 and TN=100

![](https://miro.medium.com/max/875/1*Pmpfpsj-pqJaCXXzKgtQ3Q.png)

Figure 10 Security computation for p=0.1 and TN=100

![](https://miro.medium.com/max/808/1*0EDC7fzNSnr9JytQCLI_2g.png)

Figure 11 Graph showing how the level of security is impacted by number of storeman groups nodes

From the above diagram, it is clear when the individual probability p of a Storeman node being hacked is high, the shared Storeman node mechanism shows improvement in security. When p values decrease, the security improvement is not as significant, but it still shows theoretical advantages for shared Storeman nodes.

The diagram from Figure 11 also shows that the lower number of storeman groups, the higher the security level for the overall system.

**Better flexibility**

Storeman group’s collateral is used to ensure the security of cross-chain assets; therefore, the value of cross-chain assets must not exceed the Storeman group’s collateral. Problems arise when the Storeman group’s collateral does not match the cross-chain demand, which results in poor collateral usage. An adjustment factor can be introduced into the Storeman reward mechanism to relieve this problem. But this factor is fixed during Storeman’s working cycle, so this solution is not that perfect. Using the shared Storeman group, different bridges share the same collateral pool. Bridges with more cross-chain demand will “occupy” more collateral, while bridges with less cross-chain demand will “occupy” less collateral. All this happens naturally according to the real cross-chain demand. We show this through a simple example.

Assuming there are three Storeman groups, each of which builds a direct bridge and has the same collateral of value 1000 USDT, the Actual Cross-chain Value is calculated as:

Actual Cross-chain Value = Min{Collateral, Cross-chain Demand}

The details are shown in the figure below. Then we can calculate the Collateral Usage Rate:

Collateral Usage Rate = (Total cross-chain value)/(Total collateral)

\= (500+1000+800)/(1000+1000+1000)

\= 76.7%

![](https://miro.medium.com/max/875/1*O6hp0Z6omjck2juZnvUc9g.jpeg)

Figure 12 computation of collateral usage for regular storeman groups

By shared Storeman group, we have a higher cross-chain value, which is shown in the figure below.

![](https://miro.medium.com/max/875/1*GvH-hCyPwQ6NSh6PHOqMww.jpeg)

Figure 13 computation of collateral usage for shared storeman groups

Then we can calculate the Collateral Usage Rate:

Collateral Usage Rate = (Total crosschain value)/(Total collateral)

\= 2800/(1000+1000+1000)

\= 93.3%

**Higher crosschain capacity for a single bridge**

![](https://miro.medium.com/max/875/1*_LIBk9uVk-Z_o_wcDLFS_A.jpeg)

Figure 14 comparison of crosschain capacity of regular and shared storeman groups

Through the shared Storeman group, all the bridges share the same collateral pool. While the total cross-chain capacity remains unchanged, the maximum cross-chain capacity for a single bridge increases to the value of the total collateral. This improvement helps us handle the situations where the value of cross-chain assets exceeds the collateral behind a single bridge.

**Conclusion**

Using shared storeman group, Wanchain will develop a universal crosschain mechanism to dramatically improve the scalability and security of crosschain bridges. This project is in process and there should be a shared storeman group release in the coming quarters.
