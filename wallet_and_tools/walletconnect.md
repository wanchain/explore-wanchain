![](https://cdn.nlark.com/yuque/0/2021/jpeg/2308988/1619517881490-0aca066a-0b2a-47e1-b3e7-f632a9bcfd68.jpeg)


"WalletConnect", maybe you have never noticed the name, but when you are using imToken wallet, MetaMask mobile version, TrustWallet, etc., you will scan a pop-up QR code at a Dapp (such as UniSwap) on the screen, and you then connect to your wallet and perform subsequent transaction operations. As a digital player, I believe you will be familiar with such steps.


![](https://camo.githubusercontent.com/c89d435ba9580f71d56f86b4aba6ce4e04408d416737101500ccb731c658f423/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032312f706e672f323330383938382f313631393433393835333834312d61663236306535312d353332612d343463302d623737622d6235643331653533393039612e706e6723636c69656e7449643d7539636237353063622d646639322d342666726f6d3d7061737465266865696768743d3238392669643d753463653437376337266d617267696e3d2535426f626a6563742532304f626a656374253544266f726967696e4865696768743d353738266f726967696e57696474683d32303038266f726967696e616c547970653d75726c267374617475733d646f6e65267374796c653d6e6f6e65267461736b49643d7534623638636438612d313661372d343833332d386165622d62613830343930623536622677696474683d31303034)

*The picture above is from WalletConnect official website. If copyright issue, we will delete it*


For "WalletConnect", let's take a look at the official definition: Open protocol for connecting Wallect to Dapps, which means that it is an open source protocol for connecting wallets and dApps. To put it more bluntly, WalletConnect is like a bridge through which the digital wallets on the users' mobile phones can be seamlessly connected to the dapps on the PCs.


But generally speaking, WallectConnect only supports dapps that connect to the Ethereum-based applications. On April 15th, Wanchain completed a major upgrade of the "Jupiter" version, achieving full compatibility with the EVM, which also means that Wanchain can fully adapt to the Ethereum-based dapps and tools. After the improvement and adaptation by R&D team, you can use the mobile version of MetaMask by configuring parameters and switching to Wanchain network, in this case, MetaMask mobile can fully support Wanchain-based Dapps via WallectConnect, such as WanSwap, Zookeeper, Jack's Pot, etc. In the future, we plan to allow more mobile wallets to support WalletConnect and scan QR codes to connect to more Wanchain applications.


# How to use MetaMask mobile version to scan the QR code to connect to WanSwap?


Let's take the mobile version of MetaMask to connect to WanSwap as an example. Here are the specific steps.


## 1. Configure Wanchain network on MetaMask mobile


Click the network menu at the top of the MetaMask, and select the **Custom RPC** at the bottom of the pop-up menu.


Then fill in the RPC information as shown in the figure below, and click the **Add** button:


![](https://camo.githubusercontent.com/b1f8e22ef14f2fdb67fd814aec71f44d2e7890f9ac9ffac62e537584bb619a4e/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032312f706e672f323330383938382f313631393434343537393232382d63313662376132312d666633632d346436362d626639382d3665353537663962303166332e706e6723636c69656e7449643d7539636237353063622d646639322d342666726f6d3d7061737465266865696768743d3831302669643d756536383433376434266d617267696e3d2535426f626a6563742532304f626a656374253544266e616d653d696d6167652e706e67266f726967696e4865696768743d32333430266f726967696e57696474683d31303830266f726967696e616c547970653d62696e6172792673697a653d333638343732267374617475733d646f6e65267374796c653d6e6f6e65267461736b49643d7566326162373163362d633336362d343462612d383966342d61326461653932383063302677696474683d333734
)


```
Network Name: Wanchain
New RPC URL: https://gwan-ssl.wandevs.org:56891
Chain ID:888
Currency Symbol: WAN
Block Explorer URL: https://www.wanscan.org
```


After completed the above step, you can use MetaMask to connect to the Wanchain mainnet to send transactions.


![](https://camo.githubusercontent.com/68710b741df310c489825225ec8aa56699a91fd296b3b259a469445fa5a646a5/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032312f706e672f323330383938382f313631393434343632373331312d65623531333835322d653166612d346361642d616434612d6464363935386632656463332e706e6723636c69656e7449643d7539636237353063622d646639322d342666726f6d3d7061737465266865696768743d3830382669643d753864303134623136266d617267696e3d2535426f626a6563742532304f626a656374253544266e616d653d696d6167652e706e67266f726967696e4865696768743d32333430266f726967696e57696474683d31303830266f726967696e616c547970653d62696e6172792673697a653d323636373439267374617475733d646f6e65267374796c653d6e6f6e65267461736b49643d7564363038633335322d653465632d346330382d393662632d30373431386535656331342677696474683d333733)


## can the QR code to connect to WanSwap


Visit [WanSwap official website](https://wanswap.finance/) on your computer, and click the Connect button at the top right to connect to the wallet

![](https://camo.githubusercontent.com/224755c3818b8fdf8a2dce1d5ebea2f59406efaeb77ea1303cec7639677aefd6/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032312f706e672f323330383938382f313631393434343734323937332d30656661613634322d366232332d343762382d383531622d6438333438373831363435312e706e6723636c69656e7449643d7539636237353063622d646639322d342666726f6d3d7061737465266865696768743d3335302669643d753834663561336338266d617267696e3d2535426f626a6563742532304f626a656374253544266e616d653d696d6167652e706e67266f726967696e4865696768743d353033266f726967696e57696474683d373032266f726967696e616c547970653d62696e6172792673697a653d3630303533267374617475733d646f6e65267374796c653d6e6f6e65267461736b49643d7532386230633537612d633665352d346433612d393039302d65363436653334653731612677696474683d343838)


Select the **WalletConnect**


Click the scan button at the upper right of MetaMask and scan the QR code that pops up on the computer. After scanning, the connection between MetaMask and the WanSwap will be completed.
