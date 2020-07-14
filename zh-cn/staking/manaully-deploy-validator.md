# 手动启动验证节点教程

本教程介绍如何使用gwan手动启动验证节点。此方法不需要sudo权限，不需要使用docker。

此方法适合有一定技术基础的技术人员根据自己的实际情况灵活定制使用。

（自动启动方法请见Wanchain主网验证节点创建教程）

## 下载gwan节点
首先获取最新的gwan节点，在 https://github.com/wanchain/go-wanchain/releases/tag/v2.1.2 选中适合自己操作系统的版本并下载

这里选的是Linux版本作为示范：
```
wget https://github.com/wanchain/go-wanchain/releases/download/v2.1.2/gwan-linux-amd64-2.1.2-e7e0f23d.tar.gz

tar -zxvf gwan-linux-amd64-2.1.2-e7e0f23d.tar.gz

cd gwan-linux-amd64-2.1.2-e7e0f23d
```
查看版本信息:
```
./gwan version
```
## 创建账号
使用如下命令创建账号：

```
./gwan account new 
```
输入2次密码，并得到创建好的账号地址

使用如下命令获取账号公钥：

（假设刚刚创建的地址是AAA，密码是BBB）
```
./gwan account pubkeys AAA BBB
```
得到的key1和key3是我们后续创建验证节点需要的两个公钥

**注意：是key1和key3**

## 启动gwan节点

（假设AAA是我们刚刚创建的地址）

```
./gwan --etherbase AAA --unlock AAA --mine 
```
按照提示输入密码后，节点启动

**注意：此时节点为前台运行，关闭终端或Ctrl-C后将停止**

如果需要后台运行节点可尝试使用pm2、nohup、screen或其他后台启动方式运行

## 注册验证节点

使用官方轻钱包注册，方法请见Wanchain主网验证节点创建教程
