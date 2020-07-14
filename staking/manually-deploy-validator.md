# Manually Deploy Validator

This tutorial shows you how to manually start a validator node using GWAN. This method does not require sudo privileges and does not require the use of docker.

This method is suitable for developers with the technical ability to flexibly customize and modify instructions according to their specific environment.

## Download gwan node
First get the latest gwan node, select the version for your operating system and download it at:

[https://github.com/wanchain/go-wanchain/releases/tag/v2.1.2](https://github.com/wanchain/go-wanchain/releases/tag/v2.1.2)

Here is the Linux version for your reference:
```
wget https://github.com/wanchain/go-wanchain/releases/download/v2.1.2/gwan-linux-amd64-2.1.2-e7e0f23d.tar.gz

tar -zxvf gwan-linux-amd64-2.1.2-e7e0f23d.tar.gz

cd gwan-linux-amd64-2.1.2-e7e0f23d
```
Check version information:
```
./gwan version
```
## Account Setup
Use the following script to setup a new account:

```
./gwan account new 
```
Enter password twice and get the generated account addresses

Use the following command to get the account public key:

(assuming the address just created is AAA and the password is BBB)
```
./gwan account pubkeys AAA BBB
```

The obtained key1 and key3 are the two public keys that we need to create the validator node later.

**NOTE：key1 and key3, not key2**

## Starting GWAN Node

(assuming AAA is the address we just created)

```
./gwan --etherbase AAA --unlock AAA --mine 
```
After entering the password as prompted, the node starts

**Note: At this time, the node is running in the foreground, and will be stopped after closing the terminal or Ctrl-C.**

If you need to run the node in the background, try running with pm2, nohup, screen or other background startup mode.


## Register Validator Node
You can register through the official [WanWallet](https://github.com/wanchain/wan-wallet-desktop/releases). See [instructions here](staking/node-setup-mainnet?id=node-registration).  

## Switching Node to a New Server

[See FAQ](staking/faq?id=node-switch)