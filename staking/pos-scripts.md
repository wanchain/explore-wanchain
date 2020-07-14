# Commonly Used Scripts

## Testnet Validator Node Setup Script
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployValidator.sh && chmod +x deployValidator.sh && ./deployValidator.sh
```

## Testnet Validator Node Update Script
```
rm updateValidator.sh
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateValidator.sh && chmod +x updateValidator.sh && ./updateValidator.sh
```

## Mainnet Validator Node Setup Script
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/deployMainnetValidator.sh && chmod +x deployMainnetValidator.sh && ./deployMainnetValidator.sh
```

## Mainnet Validator Node Upgrade Script
```
rm updateMainnetValidator.sh
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/updateMainnetValidator.sh && chmod +x updateMainnetValidator.sh && ./updateMainnetValidator.sh
```

## Node Restart Script
This script only works for non-deleted data restarts of docker nodes launched with the above startup and upgrade scripts.
```
wget https://raw.githubusercontent.com/wanchain/go-wanchain/develop/loadScript/restartValidator.sh && chmod +x restartValidator.sh && ./restartValidator.sh
```

## Delete Node Script
```
sudo pkill gwan
sudo docker rm gwan
```
