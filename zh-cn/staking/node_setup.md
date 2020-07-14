# 如何创建成为验证节点

## 通过脚本启动节点

### 运行脚本创建并启动validator

在ssh登录到云服务器后，执行如下命令：

```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployValidator.sh && chmod +x deployValidator.sh && ./deployValidator.sh
```

脚本将提示您输入validator的名字，这个名字用作wanstats网站上的监控显示名称，不代表区块链浏览器上的名称。

脚本将提示您输入validator账号的密码。

脚本执行完成后，将反馈validator的账号地址和2个公钥，请将其完整备份下来供后续注册使用。

如果需要重启节点，请使用如下命令：

```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/restartValidator.sh && chmod +x restartValidator.sh && ./restartValidator.sh
```

可以使用如下命令查看工作日志：

```
sudo docker logs -f gwan
```

停止日志查看按Ctrl-C

### 通过钱包注册验证节点

接下来，可通过钱包完成validator注册行为

首先确保自己的本地轻钱包，或keystore账号中有足够的wan币，beta阶段为测试币，可接受委托的验证节点需要至少50000，不可接受委托的节点至少10000。并确认账户中除此之外还有足够的交易手续费。

在轻钱包上线之前，可通过web钱包注册：https://mywanwallet.io/

在轻钱包正式版上线后，推荐使用轻钱包注册，安全性更高。

(注意，如果使用wan wallet的助记词在mywanwallet上注册，需要在填写助记词时，密码位置需要留空)

在web钱包注册时，需要注意首先在右上角选取网络。beta阶段需要选择testnet网络。

点击Contract页面，选取Staking合约。

选取Access后，在下发选取StakeIn，完成节点注册。

![img](https://github.com/wanchain/go-wanchain/blob/develop/docs/img_get_start/8.png)

！！！注意！！！

其中的`secPk`和`bn256Pk`即为上文中脚本执行完毕后返回的2个公钥。

其中`lockEpochs`为锁定时间，取值范围是7~90。

其中`feeRate`为佣金费率，取值范围是0~10000，代表0.00%~100.00%的佣金费率。

填写完成后，在下发选取钱包类型，并导入钱包。

锁定的金额，在下一页中输入。

按照提示操作，即可完成validator注册。

### 转少量交易费到验证节点

在注册完成后，还需要转账少量交易手续费到验证节点地址，用于执行POS协议的手续费。

手续费消耗一般不超过0.01 wan每比交易，因此转50 wan币到验证人账号，便可支持较长时间的使用。

请定期通过浏览器检查验证人地址的余额，保证始终有交易费可用。

至此节点已经部署完成，如果需要详细的手动操作，不使用脚本的部署流程，可以继续看下文内容。

## 手动操作完成节点部署

### 1）安装 docker(Ubuntu):

```
$ sudo wget -qO- https://get.docker.com/ | sh

$ sudo usermod -aG docker YourUserName

$ exit
``` 

### 2）使用docker中的gwan创建keystore账号：

注意：下文中的YourUserName，YourContainerID，YourAccountAddress，YourPassword，YourPK1，YourPK2均为替代词，并不是命令本身，应根据实际情况，替换成自己的定制值；

- YourUserName：替换成你的用户名；
- YourContainerID：返回的DockerID，这个不是输入的，是返回的输出信息；
- YourAccountAddress：返回的创建好的地址；
- YourPassword：设定你的自定义的合适的密码；
- YourPK1、2：返回的你账号的2个公钥信息，注册validator时需要；

```
$ docker pull wanchain/client-go:2.1.2

$ docker run -d -v /home/YourUserName/.wanchain:/root/.wanchain wanchain/client-go:2.1.2 /bin/gwan --testnet

YourContainerID

$ docker exec -it YourContainerID /bin/bash

root> gwan attach .wanchain/testnet/gwan.ipc

> personal.newAccount('YourPassword')

"YourAccountAddress"

> personal.showPublicKey("YourAccountAddress", 'YourPassword')

["YourPK1", "YourPK2"]

> exit

root> echo "YourPassword" > /root/.wanchain/pw.txt

root> exit
```

### 3）确保您的测试账户地址拥有足额的WAN测试币（运行普通验证节点至少大于10,000WAN，运行受托验证节点至少大于50,000WAN）
 
如果已经使用钱包账号申请过测试币，可以手动将测试币转账到上文创建的validator账号中，完成后续步骤。

### 4）创建一个验证节点注册脚本文件
`/home/YourUserName/.wanchain/validatorRegister.js`

```
//validatorRegister.js

// If you want to register to be a miner you can modify and use this script to run.


//-------INPUT PARAMS YOU SHOULD MODIFY TO YOURS--------------------

// tranValue is the value you want to stake in minValue is 10000 for non-delegate validator and 50000 for delegate validator 
var tranValue = "50000"

// gasValue is the value you send to miner for protocal run's gas usage.
var gasValue = 100

// validatorAddr is the validator accounts which create nearly.
var validatorAddr = ""

// secpub is the miner accounts's secpub value which is get by personal.showPublicKey
var secpub    = ""

// g1pub is the miner accounts's g1pub value which is get by personal.showPublicKey
var g1pub     = ""

// feeRate is the delegate dividend ratio if set to 10000, means it's a single miner do not accept delegate in.
// range 0 ~ 1000 ~ 10000 means 0% ~ 10.00% ~ 100.00%
var feeRate   = 1000

// lockTime do not use in POC
var lockTime  = 7

// baseAddr is the fund source account.
var baseAddr  = ""

// passwd is the fund source account password.
var passwd    = ""

//-------INPUT PARAMS YOU SHOULD MODIFY TO YOURS--------------------


//------------------RUN CODE DO NOT MODIFY------------------
personal.unlockAccount(baseAddr, passwd)
var pay = eth.sendTransaction({from:baseAddr, to:validatorAddr, value:web3.toWin(gasValue)})
var cscDefinition = [{"constant":false,"inputs":[{"name":"addr","type":"address"}],"name":"stakeAppend","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"addr","type":"address"},{"name":"lockEpochs","type":"uint256"}],"name":"stakeUpdate","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"secPk","type":"bytes"},{"name":"bn256Pk","type":"bytes"},{"name":"lockEpochs","type":"uint256"},{"name":"feeRate","type":"uint256"}],"name":"stakeIn","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"secPk","type":"bytes"},{"name":"bn256Pk","type":"bytes"},{"name":"lockEpochs","type":"uint256"},{"name":"feeRate","type":"uint256"},{"name":"maxFeeRate","type":"uint256"}],"name":"stakeRegister","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"addr","type":"address"},{"name":"renewal","type":"bool"}],"name":"partnerIn","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"delegateAddress","type":"address"}],"name":"delegateIn","outputs":[],"payable":true,"stateMutability":"payable","type":"function"},{"constant":false,"inputs":[{"name":"delegateAddress","type":"address"}],"name":"delegateOut","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"addr","type":"address"},{"name":"feeRate","type":"uint256"}],"name":"stakeUpdateFeeRate","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"v","type":"uint256"},{"indexed":false,"name":"feeRate","type":"uint256"},{"indexed":false,"name":"lockEpoch","type":"uint256"},{"indexed":false,"name":"maxFeeRate","type":"uint256"}],"name":"stakeRegister","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"v","type":"uint256"},{"indexed":false,"name":"feeRate","type":"uint256"},{"indexed":false,"name":"lockEpoch","type":"uint256"}],"name":"stakeIn","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"v","type":"uint256"}],"name":"stakeAppend","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"lockEpoch","type":"uint256"}],"name":"stakeUpdate","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"v","type":"uint256"},{"indexed":false,"name":"renewal","type":"bool"}],"name":"partnerIn","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"v","type":"uint256"}],"name":"delegateIn","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"}],"name":"delegateOut","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"sender","type":"address"},{"indexed":true,"name":"posAddress","type":"address"},{"indexed":true,"name":"feeRate","type":"uint256"}],"name":"stakeUpdateFeeRate","type":"event"}]
var contractDef = eth.contract(cscDefinition);
var cscContractAddr = "0x00000000000000000000000000000000000000DA";
var coinContract = contractDef.at(cscContractAddr);

var payload = coinContract.stakeIn.getData(secpub, g1pub, lockTime, feeRate)
var tx = eth.sendTransaction({from:baseAddr, to:cscContractAddr, value:web3.toWin(tranValue), data:payload, gas: 200000, gasprice:'0x' + (200000000000).toString(16)});
console.log("tx=" + tx)
//------------------RUN CODE DO NOT MODIFY------------------
``` 

![](media/23.png)

![](media/24.png)

脚本中的FeeRate字段为受托验证节点的委托费率，其值为0-100。如果FeeRate字段设为100，则表示受托节点不接受委托。如果FeeRate字段设为10，则表示受托节点收取委托人10%的收益后，再与委托人按共识系统设计的算法进行收益分配。如果FeeRate字段设为0，则表示受托节点不收取委托费率，即与委托人按共识系统的算法将全部收益进行分配。
 
### 5）在gwan中执行脚本
如果2）中的docker没有关闭，可以直接按下述代码进入执行，如果已关闭，请重新启动：

```
$ docker exec -it YourContainerID /bin/gwan attach .wanchain/testnet/gwan.ipc

> loadScript("/root/.wanchain/validatorRegister.js")

> exit

$ docker stop YourContainerID

$ docker run -d -p 17717:17717 -p 17717:17717/udp -v /home/YourUserName/.wanchain:/root/.wanchain wanchain/client-go:2.1.2 /bin/gwan --testnet --etherbase "YourAccountAddress" --unlock "YourAccountAddress" --password /root/.wanchain/pw.txt --mine --minerthreads=1 --wanstats your-node-name:admin@testnet.wanstats.io
```

其中参数中的“--wanstats your-node-name:admin@testnet.wanstats.io”部分是PoS beta测试用于统计节点和PoS网络运行情况的。
“your-node-name”请自定义为您想要的节点名称，例如“Community-WAN-node_EMEA1”，请避免使用大小写字母，数字，“-”，“_”以外的字符。
您可以通过WanStats网站来查看这些信息，Beta测试阶段WanStats的网址为：http://testnet.wanstats.io

执行完上述脚本，即可完成开启验证节点的权益挖矿（Staking）运行。测试者可通过 
```
docker logs -f `docker ps -q` 
```
命令查看工作日志。
注：权益挖矿工作，将在所有块同步完成后正式开始。当前测试网数据较大，同步时间可能需要几个小时，请耐心等待。

![](media/25.png)

![](media/26.png)

此外，我们提供了[如何注册成为验证节点的教学视频](https://url.cn/5KZstz4?sf=uri)，请结合上文提供的代码进行观看。

