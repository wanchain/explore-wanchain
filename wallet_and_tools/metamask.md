Using MetaMask to Connect Wanchain

![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618566292280-20327fd7-32ca-407f-89f5-eaea635ed7de.png#clientId=u39226d0b-815b-4&from=ui&id=uljNH&margin=%5Bobject%20Object%5D&originHeight=900&originWidth=1600&originalType=binary&size=2047819&status=done&style=none&taskId=ue56aa96c-233c-491c-b3ef-a61f41d7e66)


2021年4月15日，Wanchain完成了木星版本大升级，至此，Wanchain实现了全面兼容以太坊EVM。因此，以太坊上最流行的浏览器插件钱包MetaMask同样能连接Wanchain（包括Ledger、Trezor硬件钱包的支持）。


针对MetaMask连接到Wanchain，我们提供了两种配置方法。
# 方法一：快速配置


使用[chainlist.org](https://chainlist.org)网站提供的功能，可以快速添加Wanchain网络到MetaMask浏览器插件钱包中。


首先使用Chrome浏览器打开 [https://chainlist.org](https://chainlist.org)


在上方搜索框内输入**Wanchain**


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618563849482-3b8e195c-397d-47eb-a917-36a7be2ac6cd.png#clientId=u53be20a9-4ca5-4&from=paste&height=268&id=u7634b4cf&margin=%5Bobject%20Object%5D&originHeight=349&originWidth=887&originalType=binary&size=77189&status=done&style=none&taskId=ue6e2be7c-ef39-40b8-a260-0eb3335a2a4&width=680.5)


然后点击下方的**Connect Wallet**按钮，连接MetaMask。


然后点击**Add To Metamask**按钮，即可完成Wanchain网络的添加和切换。


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618563869592-57683513-122d-446b-b079-fc770e09aa65.png#clientId=u53be20a9-4ca5-4&from=paste&height=221&id=ud0035f6b&margin=%5Bobject%20Object%5D&originHeight=232&originWidth=432&originalType=binary&size=34339&status=done&style=none&taskId=u67fa4109-ea46-4c06-acf5-b345cd831bf&width=411)


添加完成后，即可在Wanchain的Dapp中选择MetaMask钱包来使用。


# 方法二：手动配置
## 连接Wanchain主网
点击MetaMask页面上方的网络菜单，在弹出的菜单最下方选择**Custom RPC** (自定义RPC) 选项。


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618564026408-60874111-1687-4946-88db-9fe6334a6d06.png#clientId=u53be20a9-4ca5-4&from=paste&height=769&id=uc879c82b&margin=%5Bobject%20Object%5D&originHeight=769&originWidth=377&originalType=binary&size=106524&status=done&style=none&taskId=ue60f7137-9ea6-487a-9b24-ced98bc370f&width=377)


然后填写如下图所示的RPC信息，并点击**Save**（保存）按钮：


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618564194973-b1d3f342-ded7-47d3-bed6-53087f99eb47.png#clientId=u53be20a9-4ca5-4&from=paste&height=552&id=u2bb049a4&margin=%5Bobject%20Object%5D&originHeight=598&originWidth=429&originalType=binary&size=41320&status=done&style=none&taskId=u066f4b26-0ffa-4910-90a7-4622a815f70&width=396)


```
Network Name: Wanchain
New RPC URL: https://gwan-ssl.wandevs.org:56891
Chain ID:888
Currency Symbol: WAN
Block Explorer URL: https://www.wanscan.org
```


添加完成即可用MetaMask连接Wanchain主网来发送交易。


## 连接Wanchain测试网


点击MetaMask页面上方的网络菜单，在弹出的菜单最下方选择**Custom RPC** (自定义RPC) 选项。


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618564372218-64385906-7c71-4c35-932e-270765ee21f1.png#clientId=u53be20a9-4ca5-4&from=paste&height=727&id=u3fb6c7f1&margin=%5Bobject%20Object%5D&originHeight=769&originWidth=377&originalType=binary&size=106524&status=done&style=none&taskId=u0397cd4e-0f21-408d-9f21-a71f275ba09&width=356.5)


然后填写如下图所示的RPC信息，并点击**Save**（保存）按钮：


![](https://cdn.nlark.com/yuque/0/2021/png/2308988/1618564407456-e59e4849-b2e3-43b9-80d6-831cda25ea1e.png#clientId=u53be20a9-4ca5-4&from=paste&height=574&id=u84e2b3b4&margin=%5Bobject%20Object%5D&originHeight=574&originWidth=385&originalType=binary&size=42703&status=done&style=none&taskId=uedb5b6a0-6324-4a2c-b950-890bb0c62f1&width=385)


```
Network Name: Wanchain
New RPC URL: https://gwan-ssl.wandevs.org:46891
Chain ID: 999
Currency Symbol: WAN
Block Explorer URL: https://testnet.wanscan.org
```


添加完成即可用MetaMask连接Wanchain测试网来发送交易。
