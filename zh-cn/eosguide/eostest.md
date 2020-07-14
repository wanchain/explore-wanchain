# Wanchain测试网EOS跨链平台测试指南

## 简介

Wanchain测试网成功跨链集成EOS！wEOS代币是EOS在Wanchain上的映射代币，可自由地用于跨链交易场景。用户可直接在Wanchain轻钱包上管理原生EOS账户，包括CPU、NET和RAM等资源，并通过钱包进行可视化操作，完成从EOS到wEOS的跨链转账。
 
EOS是Wanchain跨链集成的第三条异构公链。EOS作为是全球规模最大、活跃度最高的公链之一，此次的跨链集意义重大。因此，我们诚邀广大社区小伙伴积极参与到EOS的跨链公测中来。

## 填写EOS跨链测试申请表

请点击填写[EOS跨链测试申请表](https://wj.qq.com/s2/5335901/8851)

您所填写的申请表信息以及您接下来的测试反馈结果是我们给予测试人员一定奖励报酬的重要依据。

**测试周期：EOS跨链平台测试时间为即日起至EOS跨链平台上线Wanchain主网时止。**

## 技术测试群

您可加入中英文技术群，与更多技术大咖共同探讨EOS跨链测试：

- 国际技术群（Gitter） https://gitter.im/wandevs/community
- 国内EOS跨链技术群，请加bryan-yewei微信号，拉您进群。

## 测试资源链接汇总

- [Wan Wallet测试版钱包](https://github.com/wanchain/wan-wallet-desktop/releases/tag/v0.0.99-beta)
- [eos-cross测试版SDK](https://github.com/wanchain/wanchain-js-sdk/tree/eos-cross)
- [WAN测试币申请](http://54.201.62.90/)
- [EOS Jungle Testnet测试币申请](http://monitor.jungletestnet.io/)

## WanWallet轻钱包的EOS代币管理和跨链交易

### EOS代币管理
 
此次新版钱包能够支持多币种管理（目前囊括比特币、以太坊、EOS和WAN，以及基于以太坊、EOS和WAN网络上的生态代币）。
 
**注：启动钱包后，请手动将钱包网络从Wanchain主网切换至Wanchain测试网。建议不要将Wanchain主网上的WAN代币转入该钱包。**

**钱包启动后，弹出升级至1.1.1版本的提醒，请不要进行升级，因为升级后的版本无法进行EOS跨链交易的测试。**

**测试版钱包主页入口：https://github.com/wanchain/wan-wallet-desktop/releases/tag/v0.0.99-beta**

其中，
Windows普通用户可下载Wan-Wallet-win-0.0.99-beta.exe；
Mac普通用户可下载Wan-Wallet-mac-0.0.99-beta.dmg；
Linux普通用户可下载Wan-Wallet-linux-0.0.99-beta.AppImage。

在Wanchain轻钱包中，用户首先需要在钱包中创建密钥，然后通过EOS Jungle Testnet网站创建EOS账户，最后把EOS账户关联到Wanchain轻钱包所创建的私钥。

Wanchain轻钱包创建EOS密钥:

![](https://www.wanchain.org/wp-content/uploads/2020/01/0102-12.png)

EOS Jungle Testnet创建EOS账户：http://monitor.jungletestnet.io/#account

![](https://www.wanchain.org/wp-content/uploads/2020/01/0102-13.png)

在Wanchain轻钱包EOS界面相对于的密钥下导入已经创建好的账户：

![](https://www.wanchain.org/wp-content/uploads/2020/01/0102-14.png)

在钱包的EOS界面，用户可以看到自己创建的EOS密钥地址和账户，以及每个账户对应的EOS代币余额和资源信息。EOS界面的下方是历史交易记录。在历史交易记录区域，用户可以查询EOS代币交易和资源管理交易。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-02.png)
 
在资源管理界面，用户能够全面管理自己的EOS资源，包括RAM、CPU和NET。用户可以对NET资源和CPU资源进行质押（Stake）或赎回（Unstake）；可以对RAM资源进行买入（Buy）或卖出（Sell）。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-03.png)
 
用户可以创建新的EOS账户。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-04.png)

在交易界面，用户可以自由选择转出地址和转入地址，输入要转账的EOS数量，以及附上备注（Memo）信息。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-05.png)

在导入界面，用户可以导入其他的EOS账户。
 
![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-06.png)

在设置界面，用户可以启用（或隐藏）已经集成的WRC20和ERC20代币币种，使其显示在钱包首页。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-07.png)

轻钱包设置界面还提供了网络分析功能，用户可以清楚掌握自己的钱包到RPC服务器和各个区块链节点的网络状况。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-08.png)

当前，Wanchain已实现跨链集成BTC、ETH和EOS公链，Wanchain团队计划将跨链集成至少两条公链和一批基于ETH和EOS的生态代币。
 
### 一键跨链生成EOS的映射代币WEOS 
 
此次新版Wanchain桌面轻钱包支持了多种主流币种的跨链转账，包括BTC、ETH和EOS，以及基于ETH和EOS网络上的生态代币。

打开EOS跨链页面：

![](https://www.wanchain.org/wp-content/uploads/2020/01/0102-15.png)
 
在EOS跨链界面，用户选择Storeman地址，接收方地址和要跨链转账的EOS数量。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-09.jpg)
 
跨链转账成功后，钱包首页便可显示转账后对应的wEOS数量。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-10.png)
 
在设置界面，用户可以启动（或隐藏）已经跨链集成的WRC20和ERC20代币币种，使其显示在钱包首页。

![](https://www.wanchain.org/wp-content/uploads/2020/02/0102-11.png)

## 跨链机制的四大改进和创新
 
此次关于Wanchain跨链集成EOS，这样具有全球第二大生态规模的EOS，其所有dApp项目也将可以无缝实现万维链网络的跨链对接。这次EOS跨链项目区别于之前的ETH/ERC20/BTC，有四大新特性。
 
### 1. 跨链签名算法的升级

万维链跨链采用了基于MPC（多方计算）实现的门限签名技术，storemanGroup由多组（storeman Agent + MPC）构成，storeman Agent（以下简称Agent）同步链上数据，通过链接各自的MPC构建包含跨链数据的签名数据，MPC在P2P网络交互，达成签名共识，最终生成签名（包含智能合约交易和跨链数据）并上链，最终实现跨链。万维链目前使用的签名算法为ECDSA门限签名，这种机制要求万维链和所跨链支持MPC所使用的签名算法。

ECDSA签名算法并不是门限最优的，而且在MPC过程中计算量较大，交互次数多。为了更好的去中心化和提升跨链效率，在此次EOS跨链中使用Schnorr签名算法代替ECDSA签名算法。Schnorr签名算法满足门限最优，同时需要较低的计算量，且仅需要一次交互即可完成签名。然而目前大多数链并不支持Schnorr签名算法作为账户控制方式，为此技术团队设计了内签名机制克服这一问题。所谓内签名，就是将多方签名校验过程放到链上操作，由智能合约进行多方校验。MPC只需用Shcnorr对跨链数据进行签名，Agent（任意一个）将此签名包含到智能合约交易data中，自发签名即可上链。HTLC（哈希时间锁定）会在智能合约内部，通过Schnorr验证合约进行内签名验证，实现跨链的数据校验。Schnorr签名算法的升级和内签名的设计，理论上能够保证EOS跨链达到完全的去中心化。

### 2. MPC（安全多方计算）模块化，提供多方签名解决方案

现有的MPC需要兼容所需跨链各自的签名算法。随着BCH全面支持Schnorr签名，BTC也在不久的将来支持Schnorr签名，Schnorr被越来越多的链所接纳，使用Schnorr作为MPC的签名算法会大大提高MPC的通用性。此次跨链MPC实现模块化，并增加了单个Agent对数据签名主动授权，构建了一个基于Schnorr签名的多方签名解决方案。模块化MPC除了支持跨链平台，可以无缝接入其他需要多方签名的dApp。未来社区用户使用MPC进行多方签名，可以搭配万维链上的Schnorr签名验证合约，也可自行编写智能合约进行共识校验，从而实现dApp中的多方签名需求。
 
### 3. 通用化HTLC（哈希时间锁定）跨链合约，真正的一链跨万链的跨链平台

配合BIP-0044标准，利用链的hex ID结合账户地址编码，使用编码结果作为万维链上的注册跨链合约的唯一标识，以实现一个万维链一个HTLC跨万链的需求；同时将数据层和业务层合约分离，业务层采用可升级模式，使跨链平台更加灵动、完善，大大缩短以后跨链新业务的开发周期。
 
### 4. 释放storemanGroup（跨链节点组）锁定资金账户的角色，让跨链更加去中心化

现有的跨链技术，原链和万维链上会有storemanGroup的锁定账户，已经跨过的数字资产会存储在锁定账户上；而新版的跨链机制中，storeman只负责通过多方计算完成对跨链数据的合法签名，跨链资金会锁定在HTLC智能合约中，智能合约通过业务逻辑进行资金支配，跨链资金会更加安全。

