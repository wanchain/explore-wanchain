# WanLabs launches a new DAPP on Wanchain to bypass cross-chain transaction fees


![](https://miro.medium.com/max/3202/1*x0m6VGXrY4F0XA6xCCYmOg.png)

Wanchain’s mission is to drive blockchain adoption through interoperability by building fully decentralised bridges that connect the world’s many siloed blockchain networks. However, decentralised direct bridges between isolated blockchains are, by their very nature, bound to their origin and destination chains. Crossing these bridges triggers transactions on both ends; transactions that are subject to the unique characteristics of each chain.

For example, when crossing Wanchain’s decentralised Ethereum — Wanchain direct bridge, both Ethereum and Wanchain smart contract transactions are required. While the fees required to execute smart contracts on Wanchain are negligible, Ethereum smart contracts are expensive as they are subject to the same high Ethereum gas fees that have spawned a cottage industry of [Layer-2 solutions](https://medium.com/wanchain-foundation/lending-a-helping-hand-introducing-x-rollups-ethereum-layer-2-solution-4a995e250932).

**Enter, Instant Cross.**

[Instant Cross](https://www.instantcross.finance/) is the newest DAPP to join the Wanchain ecosystem. It is a semi-decentralised cross-chain solution developed independently by WanLabs Ltd — the team behind [WanLend](https://wanlend.finance/).

Rather than using smart contracts to lock and mint tokens each time a user triggers a cross-chain transaction, [Instant Cross](https://www.instantcross.finance/) reduces the gas fees required to transfer assets cross-chain by relying on basic transactions between wallets instead. This method is more cost-effective as gas fees for basic wallet-to-wallet transactions are a fraction of the gas fees required to execute smart contracts. This makes [Instant Cross](https://www.instantcross.finance/) especially well suited for users who only want to transfer small quantities of tokens cross-chain while minimising fees.

![](https://miro.medium.com/max/875/1*Y4JV1tuGbc3yikoIk4TnCg.png)

**Instant Cross’ value-add.**

1.  Lower fees
2.  Faster transactions
3.  Faster token integrations

**How does Instant Cross work?**

After a user initiates an [Instant Cross](https://www.instantcross.finance/) transaction, the system generates a deposit address. The user must then transfer the listed amount to this address to complete the transaction.

![](https://miro.medium.com/max/875/1*3dFVTF-5xDnzOCd7NVLMXA.png)

The “Deposit Amount” required to complete an [Instant Cross](https://www.instantcross.finance/) transaction is the sum of the amount a user wishes to transfer cross-chain and a unique identification code. In other words, if a user wants to send 1 ETH from Ethereum to Wanchain, they need to deposit slightly more than 1 ETH (e.g., 1.00000952 ETH). [Instant Cross](https://www.instantcross.finance/) uses this unique identification code to track different users’ transactions.

![](https://miro.medium.com/max/875/1*l8Uc7mkAgpUZ2d95sJnv0w.png)

After the user transfers the “Deposit Amount” to the “Deposit Address,” [Instant Cross](https://www.instantcross.finance/)’ cross-chain bot automatically tracks the transaction and then sends the cross-chain assets to the user’s recipient address. If the asset is one that is supported by Wanchain’s decentralised direct bridges, [Instant Cross](https://www.instantcross.finance/)’ cross-chain bot will pull from a pool of pre-minted assets. If the asset is one that isn’t support by Wanchain’s decentralised direct bridges, Instant Cross’ cross-chain bot will mint the asset on the destination chain for the user.

[Instant Cross](https://www.instantcross.finance/) currently supports BTC, ETH, USDT and USDC, with more tokens (🐶) to be added soon. For more information about [Instant Cross](https://www.instantcross.finance/) and [Wanlend](https://wanlend.finance/), stay tuned to WanLabs’ Twitter.

**About WanLabs**

Established in 2018, WanLabs is committed to the integration and innovation of cutting-edge blockchain technology and applications. Currently, WanLabs is focused on the development of cross-chain DeFi DApps. WanLabs currently operates WanLend and Instant Cross.
