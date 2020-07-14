# 常用脚本

## 测试网验证节点部署脚本
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployValidator.sh && chmod +x deployValidator.sh && ./deployValidator.sh
```

## 测试网验证节点升级脚本
```
rm updateValidator.sh
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateValidator.sh && chmod +x updateValidator.sh && ./updateValidator.sh
```

## 主网验证节点部署脚本
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployMainnetValidator.sh && chmod +x deployMainnetValidator.sh && ./deployMainnetValidator.sh
```

## 主网验证节点升级脚本
```
rm updateMainnetValidator.sh
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateMainnetValidator.sh && chmod +x updateMainnetValidator.sh && ./updateMainnetValidator.sh
```

## 节点重启脚本
此脚本只适用于使用上述启动和升级脚本启动的docker节点的不删数据重启
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/restartValidator.sh && chmod +x restartValidator.sh && ./restartValidator.sh
```

## 节点删除命令
```
sudo pkill gwan
sudo docker rm gwan
```
