# 测试网验证节点升级通知

Wanchain主网版本gwan已经正式上线，原本运行在测试网的验证节点，如果要继续运行测试网，请统一升级到v2.1.2版本。

如果不想继续运行测试网节点，而是想要转到运行主网节点的，请务必先注销测试网的验证节点，以保证测试网可以继续正常使用。

## 测试网验证节点升级方法

使用如下脚本，可以将验证节点升级到最新的v2.1.2版本

低于v2.1.2的版本将会停在块号4,204,545位置无法继续同步

```
$ rm updateValidator.sh
$ wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateValidator.sh && chmod +x updateValidator.sh && ./updateValidator.sh
```
升级操作执行完成后，请务必通过`sudo docker logs -f gwan`命令查看新版本gwan的工作日志，观察是否工作正常。

如果发现有 `reorg` 相关的ERROR信息，如：`Impossible reorg because reorg length is bigger than K`，这需要按照下面步骤删除链重新同步：
```
sudo docker stop gwan
sudo docker rm gwan
sudo rm -rf .wanchain/testnet/gwan
rm updateValidator.sh
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateValidator.sh && chmod +x ./updateValidator.sh && ./updateValidator.sh
```
## 测试网验证节点退出方法

使用mywanwallet注册的验证节点，可继续使用mywanwallet调用stakeUpdate接口退出，退出方法为设置locktime为0，这样下一个工作周期会自动退出。

使用loadScript加载脚本注册的验证节点，请使用 https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/stakeUpdate.js 脚本进行注销操作。使用方法为填写对应地址和密码后，将locktime值填为0后，在gwan的ipc控制台中使用loadScript()方式运行。
```
$ wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/stakeUpdate.js

$ vi stakeUpdate.js

# 修改其中的地址、密码和locktime=0

$ cp stakeUpdate.js .wanchain/

$ docker exec -it `docker ps -q` /bin/gwan attach /root/.wanchain/testnet/gwan.ipc

> loadScript('/root/.wanchain/stakeUpdate.js')

# 返回成功后，即可停止docker运行

> exit

$ sudo pkill gwan
$ sudo docker rm gwan
```

后续主网正式上线后，注册和退出均可通过GUI轻钱包执行，操作更加便捷。
