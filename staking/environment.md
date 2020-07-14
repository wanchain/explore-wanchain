# Recommended Hardware & Software

**Setup**
- We recommend using Linux or MacOS
- A wallet with the WAN you wish to stake + a small amount of WAN for service fees.
- You may use a cloud server such as AWS or run on bare metal. See our [AWS getting started guide](staking/aws.md) for more information.
- If using AWS, we recommend AWS m4.xlarge with the following configuration
  - CPU: 4
  - RAM:16G
  - Disk 256G
  
*For manual setup you also need:*
- [Docker](https://www.docker.com/)  
- Install Golang from https://golang.org/ and set GO environment variables `$GOPATH` and `$GOROOT` if you want to build from source code.
 
To get the most recent GWAN code from github：

```
$ mkdir -p $GOPATH/src/github.com/wanchain/

$ cd $GOPATH/src/github.com/wanchain/

$ git clone https://github.com/wanchain/go-wanchain.git

$ cd go-wanchain

$ git checkout develop

$ git pull

$ make
``` 

GWAN is compiled in this directory：**build/bin/gwan**
