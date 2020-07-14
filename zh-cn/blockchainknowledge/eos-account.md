# 聊聊与众不同的EOS账户及创建之道

## 写在前面

Wanchain作为一条着力打造分布式金融基础设施的跨链公链，在跨链协议、跨链标准制定、PoS机制研究、随机数生成、dApp应用场景、行业解决方案、合约设计模式等诸多方面，万维链团队有着扎实的理论基础和丰富的实践经验。秉承兼容并包的区块链精神，Wanchain团队开办“万维区块链知识大讲堂”栏目，凭借团队的技术积淀，由团队技术大咖亲自执笔，定期为整个行业贡献有趣、有价值、有意义的内容输出，为业内业外的普通用户和专业用户抛砖引玉，让万维链和社区全体成员、和整个行业共同进步。

<!--more-->

万维区块链知识大讲堂之EOS篇：解析复杂的EOS账户构成方式以及如何创建EOS账户。由Wanchain技术团队资深工程师詹力为大家徐徐道来EOS账户的道道以及如何创建EOS账户如何购买账户资源。

## 正文

### 一、账户系统

作为一个小白用户，首次接触EOS，必须需要理解的必然是EOS账户，没有一个账户，未免会有一种不得其门而入的感觉。

首先介绍下EOS和万维链的账号概念区别。与以太坊类似，万维链中，每个账户都有一个公私钥对，私钥是32字节的16进制字符，私钥可以通过椭圆曲线算法映射出公钥，而公钥通过哈希再取出后20字节（即40位16进制数）就是对应的万维链地址，每一个地址就是一个账户。

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-01.png)

EOS引入了账户系统的概念，其中包含Account账户，Wallet钱包，钱包密码，key公私钥对，Permission权限等概念。说到EOS的账号系统，大家都喜欢用下面的图进行解释。

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-02.png)

#### 账户

EOS的账号包含了一个账户名，这个账户名会关联对应的EOS智能合约和Token。EOS的账户不再是一串很长的16进制字符，而是类似于电脑用户名，是一个用户自己定义的小写英文字符（a~z）+数字（12345）+符号(.)，最长12位，最短1位，全链唯一；账户名使用注册机制，先到先得，12位以下的账户，需要通过竞拍获得。

#### 钱包

钱包是用来存储私钥的地方，打开之后的钱包有两种状态，解锁状态和锁定状态。私钥和公钥一一对应，Wallet钱包通过独立的密码，保管私钥，通过输入密码可以解锁钱包，读取私钥，进行私钥管理账户的对应权限签名。失去钱包的密码，也就意味着你失去了私钥。

#### 权限

在EOS的账户体系设计中，账户默认初始化有两个权限，owner和active权限，用户也可以自定义新的权限，每个权限的使用又有权重和阈值的概念（后面介绍多重签名会进行介绍），而每一个权限用户可以绑定到一个或者多个公钥上，或者将权限和另一个有效账户进行绑定。

owner权限：顾名思义，是声明这个账号的归属，owner权限可以用来管理active和其他权限，极少数交易会使用到owner权限，建议对owner权限的私钥进行冷存储。

Active权限：一般用来进行转账/投票/发起其他交易的常规操作。

自定义权限：名称/功能用户自己设定，EOS的权限可扩展性，让开发更加灵活。

### 二、资源

了解了EOS的账户系统，是不是就可以创建自己的账户了？不是，你还需要了解EOS的资源系统。习惯了BTC/ETH/WAN的用户，初次探访EOS肯定会对资源一头雾水，如果有了账户，账户里面有了对应的EOS余额，为什么还要资源，这不得不要说一下EOS的资源系统。如果把EOS理解成操作系统，可能会更容易理解，账户名类似于操作系统的用户名，而资源也类似，EOS的资源系统由RAM, CPU和NET组成，一个EOS账户需有有了对应的资源，用户才能够玩的转。

#### RAM

RAM即内存，EOS系统中，账户信息/智能合约执行的当前状态，都是存储在内存中的，而数据存储在区块链中要长期占用资源。RAM可以通过抵押EOS到系统账户进行购买，抵押和解除抵押通过执行EOS系统智能合约buyram和sellram进行实现，每笔收取0.5%的手续费，同时RAM的价格也是一直变动，并且由于RAM类似于操作系统，是一种物理资产，不扩容的情况下，是一种稀缺资源，这也是为什么EOS会存在炒RAM的情况。

#### NET/CPU

用户发起一笔普通交易(调用系统合约)或者其他智能合约时，区块生产者需要将交易打包，并将区块同步给其他生产者，这就需要消耗一定的网络带宽资源NET;而智能合约查询合约代码，加载到内存执行，都需要消耗一定的EOS系统算力，也就是CPU。用户获取NET/CPU有两种方式，一种是通过抵押自己的EOS给系统账户，进行获取，第二种是通过在其他用户手中租赁，其他用户抵押EOS使之获取对应资源。CPU和NET是一种时间资源，抵押的EOS数量所占全网的比例，会决定了能够获取的CPU/NET资源数量，抵押的EOS赎回需要三天左右的赎回期。租赁的资源在赎回时，EOS会回到原有用户的账户中。

### 三、创建账户

小白习惯了BTC/ETH/WAN创建地址是免费的，使用钱包工具可以很方便的获取到新的地址账户，而对于号称使用免费的EOS肯定有着疑问，创建账户竟然是收费的？了解了上面的资源系统，多少就能理解为什么创建EOS账户需要收费，因为账户的存储需要占用新的资源。这点有点像很多俱乐部，需要先有会员邀请才能够加入，只有通过现有账户花费资源才能够创建新的EOS账户。如果用户已经有了EOS账户，可以通过wanchain的light wallet多币种钱包进行私钥导入/创建新账户/资源管理，https://github.com/wanchain/wan-wallet-desktop/releases 。

#### 主网账户创建

用户如果想创建第一个账户，可以通过一些公开的网直进行创建，如https://www.signupeos.com/ 、https://eos-account-creator.com/ 等。收取的 EOS 费用，计算方式将由这几个部分组成

1. 账号初始 CPU 资源抵押消耗 0.15 EOS，NET 资源抵押消耗0.05 EOS

2. 初始内存 0.4Kb 的购买费用，价格根据当前市场波动，

3. 开发维护费，多余的费用会直接转到新创建的账户中。

Signupeos 支持EOS交易所转账（memo必须要填写正确）和微信wechat转账，eos-account-creator支持信用卡支付，友情提示，微信支付相对费用较高哦，记得一定要存储好自己的公私钥对。Owner和active建议使用不同的公私钥对。

注：上述主网账户创建地址仅为列举的可参考地址，不代表官方推荐，请仔细甄别。

#### a. 使用signupeos进行创建

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-03.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-04.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-05.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-06-副本.png)

#### b. 使用eos-account-creator 进行创建

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-07.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-08.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-09.png)

#### 测试网账户创建

测试网介绍Jungle的创建方式，http://monitor.jungletestnet.io/ 网站进行创建，“Create keys”进行公私钥对创建，“create account”进行账户创建，“faucet”进行测试币申请。

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-10.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-11.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-12.png)

### 四、资源购买

如果你以为创建好了账号，就可以使用了，你会发现自己陷入一个鸡生蛋/蛋生鸡的无限死循环中，现在的EOS主网资源RAM/CPU费用已经比最开始的时候贵了很多，创建账户的初始资源0.2 EOS的RAM，0.15 EOS的CPU以及0.05 EOS的NET，根本支付不起一笔最简单的transfer交易，你还需要租赁资源才能够真正开始EOS的探索里程。

我们找到一个主网使用signupeos新创建的账户quanyisheng5，账户信息可以参考网页https://bloks.io/account/quanyisheng5 。可以看到signupeos给新账户quanyisheng5质押了0.2217 EOS购买RAM, 0.15 EOS的CPU以及0.05 EOS的NET,按照当时的市场价格，共计13 µs CPU和51kb NET,一笔普通的EOS转账需要消耗170 µs和128Bytes，https://bloks.io/transaction/e33ac177c61351b135845710145ab6ef7937f1e08207a133662039e7d77122fa ，所以初始账户还需要别的账户进行质押资源才能够开始交易。

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-13.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-14.png)

![](https://www.wanchain.org/wp-content/uploads/2020/04/0424-15.png)

租赁平台可以参考，一个是https://eoslaomao.com/bankofstaked ，这个是laomao超级节点开发的一个租赁平台,目前有个免费套餐，第二个是https://meet.one/eostools/meetonestake.html ，可以支持发笔租赁；以上资源来自CSDN“EOSCPU租赁市场现状及各种坑”https://blog.csdn.net/ITleaks/article/details/83538610 。

注：上述租赁平台地址仅为列举的可参考地址，不代表官方推荐，请仔细甄别。

## 关于Wanchain

Wanchain，中文名万维链，聚焦于跨链机制的研发，通过构建具有跨链能力的分布式金融基础设施来实现万链互联的宏伟目标。截至目前，Wanchain已成功跨链集成比特币、以太坊、EOS以及以太坊和EOS上的生态代币，并设计提出了通用跨链框架T-Bridge，旨在实现资产和数据在不同公链和联盟链间的自由流转。在共识机制方面，Wanchain设计并上线了拥有完整委托机制的实用PoS共识协议，即星系共识。不论是跨链机制，还是共识协议，Wanchain一直处于行业的领先位置。

扫描关注微信公众号万维链(id: WanchainCN)，获取更多信息

![](https://www.wanchain.org/wp-content/uploads/2020/04/WanchainQRCode.jpg)
