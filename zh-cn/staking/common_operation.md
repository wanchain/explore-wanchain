# 常用操作
### 账号创建
```
$ gwan account new
```

执行上述命令后，keystore文件会存储在默认目录 `~/.wanchain/keystore/` in Ubuntu 或者 `~/Library/Wanchain/keystore/` in Mac OS.

使用如下命令获取两个星系共识需要用到的公钥。

```
$ gwan account pubkeys 'Your Address' 'Your Password'
```

星系共识需要使用key1和key3，作为SecPk和G1PK。

### 查询余额

```
// In ubuntu
$ gwan attach ~/.wanchain/gwan.ipc

// In MacOS
$ gwan attach ~/Library/Wanchain/gwan.ipc
```

在链同步完成后，可通过下面指令查询余额。

```
$ eth.getBalance("Your Address Fill Here")

// Such as address example shown above.
$ eth.getBalance("0x8c35B69AC00EC3dA29a84C40842dfdD594Bf5d27")
```

### 获取测试币

请登录http://wanchain.mikecrm.com/USjDMuk 进行填表申请。
 

### 如何运行两大节点

#### 非验证节点（全节点）
```
$ gwan --rpc --syncmode "full"
``` 

#### 验证节点

在下面命令中请替换地址为您的个人地址 `0x8d8e7c0813a51d3bd1d08246af2a8a7a57d8922e` ，并替换 `/tmp/pw.txt` 为您地址的密码文本文件。

```
$ gwan --rpc --etherbase "0x8d8e7c0813a51d3bd1d08246af2a8a7a57d8922e" --unlock "0x8d8e7c0813a51d3bd1d08246af2a8a7a57d8922e" --password /tmp/pw.txt--rpc  --mine --minerthreads=1 --syncmode "full"
```

### Stake注册和委托投注

用户注册一个节点服务器为星系共识验证节点的步骤如下图所示：

![](media/32.png)

### 退本金方法

#### 验证节点退本金

验证人可使用[stakeUpdate.js](https://github.com/wanchain/go-wanchain/blob/develop/loadScript/stakeUpdate.js)脚本，将locktime设成0，来实现退款。本金将在下个周期开始时，自动退回来源账户。

默认情况下，验证人会自动续期。需要手动操作才能退本金。

#### 委托人退本金

通过钱包投注的委托人，可直接通过钱包的退款按钮退款。

通过脚本注册的委托人，可通过delegateOut.js脚本完成退本金操作。
