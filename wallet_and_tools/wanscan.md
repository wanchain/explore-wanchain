# Wanchain Blockchain Explorer

## 0. Introduction
Go to [wanscan.org](https://www.wanscan.org/) to see Wanchain Blockchain Explorer. You can query all the data on the blockchain, including the balance of any address, transaction records; check node status, various tokens issued, and cross-chain data, etc.

The homepage displays data such as the block height, the total staked assets of PoS and Storemen, the average APY, and the top ten nodes, the latest blocks, the latest transactions and other information.

At the same time, in the text box at the upper right corner of the page, you can enter block height, Txhash, wallet address, token address and other information for direct query. The blockchain browser is very convenient and will automatically recognize and output the corresponding results.

![](https://camo.githubusercontent.com/c7e55710c31472016c1de67b419377e9ee7c9d0f17916a0c1663307a2b6f5379/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032302f706e672f323632363838372f313630353735383332353439392d35383534383739382d393930332d346534372d396139362d3536633731363432363430372e706e673f782d6f73732d70726f636573733d696d616765253246726573697a65253243775f31343932)


## 1. 查看账户
如果是查询账户余额、账户的历史交易数据等信息，建议直接输入钱包地址查询；
除此之外，你还可以看到账户里各种代币的余额和交易数据，跨链数据，节点奖励，委托奖励等信息；![地址.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602833893850-1e149fc7-dee6-4bfa-8436-b3f7ab8f101d.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E5%9C%B0%E5%9D%80.png&originHeight=1080&originWidth=1841&size=105883&status=done&style=none&width=1841)


## 2. 查看单笔交易
如果是查询某笔交易的详细信息，输入交易哈希是最方便的。
你可以非常清晰地看到交易的状态、区块高度、时间戳、发送方和接收方的地址、gas数据、交易额等信息。![交易哈希.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834021062-3d7f5688-790b-4c82-ae99-fd19edfd542d.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E4%BA%A4%E6%98%93%E5%93%88%E5%B8%8C.png&originHeight=1080&originWidth=1841&size=60440&status=done&style=none&width=1841)


## 3. 查询区块
在这个页面里，你可以看到该区块的所有信息，包括区块高度，区块哈希、区块年龄（时间戳），区块详情，以及区块对应的字节大小等。
![区块高度.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834047619-4c799ad4-8284-4221-8399-43bd66a97b63.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E5%8C%BA%E5%9D%97%E9%AB%98%E5%BA%A6.png&originHeight=1080&originWidth=1841&size=72922&status=done&style=none&width=1841)
 
## 4. 查看PoS节点
在首页前十节点（Top 10 Validators）的右侧，可查看全部节点（View All）。节点分两类：受托验证节点和普通验证节点，通过是否接受委托（Accept Delegations）来区分。
大家想参与星系共识PoS来赚取更多的WAN时，一般都会找委托费率低，质押量大的受托验证节点。对于委托费率，可参考节点的当前费率（Current Fee）和最高费率（Max Fee）。![节点列表.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834460024-0a67475d-41db-4859-b9b6-c2bb77e0fc5c.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E8%8A%82%E7%82%B9%E5%88%97%E8%A1%A8.png&originHeight=1080&originWidth=1840&size=128501&status=done&style=none&width=1840)
点击节点的名称，可进入查看该节点的详细信息，如节点的地址（Address），开启的时间（Start Time），锁定周期（Lock Period），获得奖励的WAN总数（Total Reward）和详细记录（Validator Reward），委托人数量（Delegations）和列表（Delegator List）等信息。 ![节点信息.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834468134-90d731ab-3b82-4b55-b01a-6a632c160cad.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E8%8A%82%E7%82%B9%E4%BF%A1%E6%81%AF.png&originHeight=1080&originWidth=1841&size=94689&status=done&style=none&width=1841)
你还可到 [https://wanstats.io/](https://wanstats.io/)网站上查看各节点的运行监控信息。![节点监控.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834117071-a197a134-2093-4a8e-a724-f678d9dc12fa.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E8%8A%82%E7%82%B9%E7%9B%91%E6%8E%A7.png&originHeight=1080&originWidth=1841&size=161648&status=done&style=none&width=1841)



## 5. 查看Storeman节点


在跨链节点组列表中，你可以看到各个节点组的名称（Identity）、跨链对（Cross Chain）、质押币的数量（Deposit）、当前状态（Status）、委托费率（Delegate Fee）、以及开始（Start Time）、结束时间（End Time）；
![storeman1.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1605673741681-3221abfe-445c-4290-b921-2b8e2e5e66f3.png#align=left&display=inline&height=668&margin=%5Bobject%20Object%5D&name=storeman1.png&originHeight=668&originWidth=1672&size=47995&status=done&style=none&width=1672)

点击节点组的名称，可以查看该节点组的详细情况，除了上面提及的那些信息外，还有竞选时间段（Selecting Time）、协商时间段（Negotiating Time）、工作时间段（Working Time）、节点名称或地址（Address）、权重（Power Weight）、竞选排名（Rank）、是否自动续期（Auto Renew）、活跃度（Activity）等。
![storeman2.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1605673772855-2d335bb1-c5e1-4155-ad37-0c41bba6447f.png#align=left&display=inline&height=1071&margin=%5Bobject%20Object%5D&name=storeman2.png&originHeight=1071&originWidth=1672&size=86104&status=done&style=none&width=1672)


## 6. 查看代币信息
点击顶部导航栏“TOKENS”可以看到在Wanchain上发行的所有代币的列表。
点击代币名称，即可查看该代币的详细信息，如总发行量，交易数量和详细列表，持有者地址等。![代币列表.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834139385-ce6b8870-022e-4f28-9782-283cbc160e64.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E4%BB%A3%E5%B8%81%E5%88%97%E8%A1%A8.png&originHeight=1080&originWidth=1841&size=94365&status=done&style=none&width=1841)


## 7. 查看交易列表
点击顶部导航栏“TRANSACTIONS”，你可以看到所有的交易记录。![交易列表.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834387153-c5d12705-d713-4c4a-85d4-6c57c78bca9d.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E4%BA%A4%E6%98%93%E5%88%97%E8%A1%A8.png&originHeight=1080&originWidth=1842&size=122545&status=done&style=none&width=1842)
而点击 “CROSS-CHAIN”，看到的是所有的跨链交易。![跨链交易.png](https://cdn.nlark.com/yuque/0/2020/png/2626887/1602834179277-50b785b7-95b1-45c7-b79d-e2bdbe8ed047.png#align=left&display=inline&height=1080&margin=%5Bobject%20Object%5D&name=%E8%B7%A8%E9%93%BE%E4%BA%A4%E6%98%93.png&originHeight=1080&originWidth=1841&size=116227&status=done&style=none&width=1841)
## 8. 查看Wanchain的GitHub信息
点击顶部导航栏“GITHUB”，你可以看到在Wanchain的GitHub信息。或直接在浏览器中输入[https://github.com/wanchain](https://github.com/wanchain) 查看。


感谢您使用[wanscan.org](https://www.wanscan.org/)。如您有任何疑问，可发送邮件到[techsupport@wanchain.org](mailto:techsupport@wanchain.org)，或者直接在我们的微信群、电报群反馈。


Wanchain感谢您的支持！
