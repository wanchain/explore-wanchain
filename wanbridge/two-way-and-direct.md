# Understanding Wanchain Two-Way Bridge and Direct Bridge for crosschain operations

Wanchain is a blockchain project that focuses on building bridges to connect with public or private, homogeneous or heterogeneous, blockchains. From Wanchain 2.0 to Wanchain 5.0, Wanchain has connected with various blockchains such as Ethereum, Bitcoin, and EOS. For 5.0, Wanchain releases two-way bridge to connect with Ethereum blockchain through the Open Storeman mechanism. This has achieved the technical framework as laid out in the Wanchain whitepaper. Going beyond that, Wanchain has been working on direct bridge that will connect two public blockchains without the need of routing through a hub blockchain as shown in the following architectural diagram extended from Wanchain’s original whitepaper.

![](https://miro.medium.com/max/1920/1*MPwZehLoF1Eg1G_Nn68gmQ.jpeg)

Wanchain expands crosschain architecture to two way bridge and direct bridge

In this article, we describe in details some basic concepts, features, and processes for two-way bridge and direct bridge.

## Two-Way Crosschain Bridge

Not all bridges are the same. A bridge in the context of this article is a platform that can transfer assets from one blockchain to another blockchain. There are three elements that are important to describe a crosschain bridge: a) who provides the bridge; b) what assets are transferred in a bridge; c) on what blockchain the assets reside. As crosschain technology and applications are still at an early stage and there are only a few applications that provide solutions for bridging assets in different blockchains, there are many conceptions that need to be clarified to better understand crosschain bridges. For example, we used the word “wrapped ether” to represent ether in its ERC20 format and “wrapped BTC” for BTC in its ERC20 format. This is very inaccurate as the first one is on its native chain and the other is crossed from another blockchain. It is very important to differentiate an asset crossed from another blockchain as the value of this asset depends on the security of the existing chain, the source chain, and the bridges that connect the two.

We would also think intuitively that all bridges are two-way bridges, as assets transferred from blockchain A to blockchain B should be able to be redeemed back to its original chain. However, if we look at all the solutions that are provided for crosschain bridges, the asset transfers are only unidirectional as almost all solutions are to bring assets to Ethereum blockchain. It is very rare for Ether to be transferred to other blockchains.

To better understand a two-way bridge, it is important to know that assets in crosschain system can have two distinct forms: one is native assets that are generated from its source blockchain, and another is transformed assets that are minted after locking assets in its parent blockchain. For example, in Ethereum blockchain, Ether and most of the ERC20 tokens, are native assets, while wrapped ERC20 tokens, such as wBTC and wanBTC, are transformed assets. Transformed assets are created through crosschain bridges, most of them centralized. Native assets can exist standalone in its source blockchain, while transformed assets cannot exist independent of its locked native assets. Here, we use the term “transformed asset” to mean an asset that is locked in its source chain and minted in the target chain. Several other terms such as “derived asset,” “wrapped asset,” or “foreign asset” can also be used to describe this important conception in the crosschain bridge.

Due to different blockchains having different consensus, cryptography, and smart contract support, not all crosschain asset-transfers are supported. For example, it is easy to transform a BTC asset from bitcoin blockchain to Ethereum blockchain, but it is not easy to transfer an Ether from Ethereum blockchain to bitcoin blockchain due to lack of smart contract support on Ethereum blockchain. Hence, we call this a one-way bridge. A one-way bridge is a bridge that allows a user to transfer a native asset one-directionally from a source blockchain to a transformed asset in a target blockchain and redeem the asset back to its source form. A one-way bridge does not support transferring a native asset in a target blockchain to another asset in source blockchain. This is currently the case for most of the bridges that support asset transfer.

Before Wanchain 5.0, all Wanchain bridges were one-way bridges, as Wanchain could transfer native assets in Bitcoin, Ethereum, and EOS blockchain to Wanchain, but did not support transferring native Wancoin from Wanchain to external blockchains. Wanchain 5.0 expands this feature to support two-way bridges, meaning that Wancoin assets can be transferred to Ethereum blockchain, and Ethereum assets can be transferred to Wanchain blockchain. This allows Wanchain assets to participate in decentralized applications in Ethreum and vice-versa, allowing Ethereum native assets to be transferred to Wanchain for dapps that are faster and with lower gas fees.

## Wanchain <-> Ethereum two way bridge supported assets

Wanchain 5.0 supports two-way bridge asset transfer for Wanchain and Ethereum blockchain. The following table shows the supported asset types. To better understand the table, we briefly mention the notation used in the Wanchain crosschain representation. This set of notations is also in discussion in the Enterprise Ethereum Alliance (EEA) Crosschain Interoperability Task Force as a candidate to describe crosschain assets.

In the crosschain assets representation, three factors need to be described: the provider of the token, the taken symbol, and the blockchain in which the asset resides. A crosschain asset is represented as: \[provider\]TOKENSYMBOL@Chainname

Here, TOKENSYMBOL is the conventional token symbol, such as ETH for Ether, BTC for Bitcoin Classic, WAN for Wancoin, etc. “Provider” represents a project team name or a mechanism that creates the token. The “provider” can be omitted if it is unique and the same as the token symbol. “@Blockchain” is to represent the assets’ blockchain.

In this table, WAN@Wanchain means WAN token in Wanchain blockchain. This is a native asset of Wanchain and is what we normally call “WAN.” WAN@Ethereum is a transformed asset of WAN on Ethereum blockchain. WAN@Ethereum is in ERC20 format. Similarly, ETH@Ethereum is the native asset of Ether in Ethereum blockchain. And wanETH@Wanchain represents transformed ETH onto Wanchain by Wanchain bridge. If in the future, another project team called me2 creates another bridge to transfer ETH to Wanchain, then the transformed asset would be named as me2ETH@Wanchain.

![](https://miro.medium.com/max/875/1*9nzUad7Hl2ju4jgp3NhgZg.png)

From the supported asset transfer table above, it is shown that native assets of WAN@Wanchain can be transferred to asset of WAN@Ethereum on Ethereum blockchain. Also, native assets of ETH on Ethereum blockchain can be transferred to wanETH@Wanchain on Wanchain blockchain. Hence, we call the bridge that enables mutual transfer of native assets between two blockchains as “Two-Way Bridge.”

## Two-way bridge asset transfer with Wanwallet

Using two-way bridge to transfer assets crosschain through Wanwallet is very straightforward. The Wanwallet provides a multi-chain wallet that stores assets for both Ethereum blockchains. User just need to pick a source asset from the account list, choose the target chain, choose the bridge provider (open storeman), choose or enter the target account address, enter the amount to transfer, and then confirm to start a transfer.

![](https://miro.medium.com/max/835/1*HSN54DqYa729hH2K7Et9Eg.png)

![](https://miro.medium.com/max/733/1*ZIMlyo4awSYkc7qpsKGZ4Q.png)

From the above description of scenarios, it is clear that with Wanchain 5.0, assets can transferred from Wanchain to Ethereum blockchains back and forth with a simple user experience and work flow.

## Wanchain Direct Bridge

Up to Wanchain 5.0, all crosschain transfers supported by Wanchain were about transferring assets through Wanchain. A direct bridge platform is to expand the Wanchain platform to support asset transfer between two blockchains without the need of routing through Wanchain. This will allow Wanchain to provide a technical mechanism to bridge Bitcoin, Ethereum, Polkadot, and EOS blockchains directly. Using similar crosschain asset transfer syntax, we should support the following crosschain transfer use cases for Ethereum and Bitcoin direct bridge:

BTC@Bitcoin->wanBTC@Ethereum

This is to transfer native Bitcoin from bitcoin blockchain to wanBTC ERC20 format token in Ethereum Blockchain. wanBTC can then be used for DeFi applications in Ethereum blockchain that supports ERC20 format tokens.

wanBTC@Ethereum->BTC@Bitcoin

This is to transfer the transformed BTC in Ethereum blockchain back to its native BTC in Bitcoin blockchain.

## Other questions about direct and two-way bridges

_Will direct bridge still leverage Wanchain blockchain?_

Wanchain will not be involved in the transaction data flow in a direct bridge. However, the staking of bridge assets will be done on Wanchain. The security of a bridge is guaranteed by staking assets onto Wanchain through smart contracts. The registration for staking and delegation will remain the same. There is a possibility that multiple assets can be used as collaterals for staking.

_How are crosschain transaction fee calculated?_

For direct bridge, there are two crosschain fees, one is the transaction fee on the native blockchain: this fee is paid in its native gas fee. The other one is crosschain fee: this can be decided by the community and might be waived initially.

_Are two-way bridge and direct bridge mutually exclusive?_

No. A direct bridge can be a one-way direct bridge or two-way direct bridge. Two-way bridge deals with asset transfer directions for NATIVE assets, rather than transformed assets. If a bridge connects blockchain A and B, and native assets can be transferred from blockchain A to B as well as from blockchain B to A, this bridge is called a two-way bridge. Whereas, if a native asset can only be transferred from blockchain A to B, but not the other way, then this bridge is called one-way bridge. Note that when we define one-way or two-way bridge, we only take native asset transfer into consideration, because transformed assets can always be redeemed back to its native asset form.

_Aren’t all bridges two-way bridges? Otherwise, how can we redeem the assets back to its source chain?_

Not all assets are the same. Here, we introduce the concept of native assets and transformed assets. For a crosschain transfer, the asset in the source chain is locked, rather than destroyed. The value of the transferred assets still reside in the locked assets in the source chain. One-way bridge means that a native asset in blockchain A can be transferred to transformed asset in blockchain B, while the transfer in the other direction is not allowed. For example, several projects provide transferring Bitcoin to Ethereum blockchain, but no project provides transferring Ether to Bitcoin blockchain. So all bridges between Bitcoin and Ethereum blockchain are one-way bridge only so far. A two-way bridge means that native assets can transfer from blockchain A to B and vice versa from blockchain B to A.

## Feedback

We are collecting feedback for direct bridge. If you have any comments, please send them to Wanchain, and we will address them properly.
