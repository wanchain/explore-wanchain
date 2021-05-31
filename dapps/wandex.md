# Wan DEX introduction

WanDex is a decentralized exchange framework developed by Wanchain community developers and is based on the principle of "off-chain matching and on-chain settlement".

It provides real utility value for Wanchain's cross-chained assets, and it is the world's first cross-chain DEX platform.

WanDex supports cross-chain transaction feature for a group of major crypto-currencies, such as BTC, ETH, EOS, and various ERC20 tokens on their mainnet.

Developers and operators can easily and freely create their own DEX on Wanchain using WanDex framework.

You can customize your DEX rendering using open source front-end codes, and add any marketing campaign policy or other interesting features to your DEX.

Multiple DEX based on WanDex framework can share a common order book for the same trading pair.

All DEX based on WanDex framework can have their own unique trading pairs.


![UI](/technology/media/01wandex.png)

Main components of WanDex can be categorized into three groups:

- Fully open source [front-end code](https://github.com/wandevs/dex-front-end)
- Fully open source [smart contract source code](https://github.com/wandevs/dex-smart-contract)
- Open-source community controlled [off-chain matching engine](https://demodex.wandevs.org:43001/)

Its workflow and interaction between components are shown in the following:

![workflow and interaction between components](/technology/media/02wandex.png)

User's crypto-asset is controlled by user's own blockchain wallet and can be verified on the blockchain at any time.

Different DEX operators can modify their web interface or mobile application based on open source front-end code for users to browse and place orders.

After the order is completed in the matching engine, it is settled in a smart contract on the chain.

Only orders authorized by user's signature will trigger asset transfer during settlement phase.

Different DEX can leverage from their own unique trading pairs, transaction fee policy and shared order book.

WanDex's API uses restful mode, real-time information feed uses WebSocket interface to trigger notifications.

The back-end components framework is shown in the following figure:

![schematic diagram of back-end frame](/technology/media/03wandex.png)
