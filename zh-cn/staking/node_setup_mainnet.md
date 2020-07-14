# Wanchain主网验证节点创建教程
本教程将引导您在新创建的云服务节点上部署和运行主网验证节点。

节点启动后，通过新版本官方轻钱包来完成验证节点注册。

（此教程在节点启动时将使用最新的docker镜像来启动节点。在运行过程中，将使用sudo权限。如果您不希望使用sudo权限，请查看手动启动节点教程，使用手动下载gwan的方式来运行节点）

## 运行脚本创建并启动validator


在ssh登录到云服务器后，执行如下命令：

```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployMainnetValidator.sh && chmod +x deployMainnetValidator.sh && ./deployMainnetValidator.sh
```

脚本将提示您输入validator的名字，这个名字用作wanstats网站上的监控显示名称，不代表区块链浏览器上的名称。

脚本将提示您输入validator账号的密码。在输入密码时屏幕上看不到任何输入的内容是正常的，输入完成后按回车即可。

脚本将提示您进行密码二次确认。

**请务必牢记此密码并妥善备份，此密码如果遗失没有任何办法可以恢复**

脚本执行完成后，会输出Important提示，包括：validator地址、2个公钥以及keystore的json内容，**请将其完整备份**下来供后续注册使用。

当节点运行发生意外导致数据全部丢失时，可用此备份内容配合密码恢复全部信息，所以请务必妥善备份。


可以使用如下命令查看工作日志：

```
sudo docker logs -f gwan
```

停止日志查看按Ctrl-C

如果看到Validator Start Success字样，则节点已经启动成功，并开始链同步。

可到 https://wanstats.io/ 网站上查看节点的运行监控信息。

## 使用官方轻钱包注册节点

首先到 https://github.com/wanchain/wan-wallet-desktop/releases 下载并安装最新版本轻钱包。

首次运行轻钱包时，会提示您创建并备份助记词。请**妥善备份助记词**，它是数据丢失后恢复钱包信息的唯一途径。

向钱包WAN地址转账，并等待到账。

点击上方Setting菜单，在language选项下选中合适的语言，如中文（简体）。

点击钱包左侧设置->星系共识选项->勾选显示验证人菜单。

展开左侧星系共识页，即可看到验证人页面。

在验证人页面点击注册按钮。

按照提示信息，填写上文中备份的公钥信息。请按顺序依次填入2个公钥字符串。第一个是65个字符，第二个是64个字符，钱包会自动校验长度是否正确。

适当的填写剩余信息，选择金额充足的本地账户，完成验证节点注册。

注册成功后，可在 https://wanscan.org/ 网站上Validator列表，more选项中查看到刚刚注册的validator地址。（与上文备份的地址相同）











