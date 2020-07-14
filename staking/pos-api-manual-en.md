# Wanchain GWAN PoS API Manual

The API interface can be called after a user links to a GWAN node through IPC or RPC.

This manual lists and explains all POS-APIs.

# Contents
<!-- TOC -->
- [1. PoS-API](#3-pos-api)
    - [1.1. Basic Info Queries](#_11-basic-info-queries)
        - [1.1.1. version](#_111-version)
        - [1.1.2. getPosInfo](#_112-getposinfo)
        - [1.1.3. getEpochID](#_113-getepochid)
        - [1.1.4. getEpochBlkCnt](#_114-getepochblkcnt)
        - [1.1.5. getEpochIDByTime](#_115-getepochidbytime)
        - [1.1.6. getEpochIdByBlockNumber](#_116-getepochidbyblocknumber)
        - [1.1.7. getSlotID](#_117-getslotid)
        - [1.1.8. getSlotCount](#_118-getslotcount)
        - [1.1.9. getSlotIDByTime](#_119-getslotidbytime)
        - [1.1.10. getSlotTime](#_1110-getslottime)
        - [1.1.11. getChainQuality](#_1111-getchainquality)
        - [1.1.12. getLocalPK](#_1112-getlocalpk)
        - [1.1.13. getMaxStableBlkNumber](#_1113-getmaxstableblknumber)
        - [1.1.14. getReorgState](#_1114-getreorgstate)
        - [1.1.15. getTimeByEpochID](#_1115-gettimebyepochid)
        - [1.1.16. getWhiteListConfig](#_1116-getwhitelistconfig)
        - [1.1.17. getWhiteListbyEpochID](#_1117-getwhitelistbyepochid)
    - [1.2. Reward Info Queries](#_12-reward-info-queries)
        - [1.2.1. getEpochIncentivePayDetail](#_121-getepochincentivepaydetail)
        - [1.2.2. getEpochIncentiveBlockNumber](#_122-getepochincentiveblocknumber)
        - [1.2.3. getEpochIncentive](#_123-getepochincentive)
        - [1.2.4. getEpochGasPool](#_124-getepochgaspool)
        - [1.2.5. getEpochRemain](#_125-getepochremain)
        - [1.2.6. getIncentivePool](#_126-getincentivepool)
    - [1.3. Election Information Queries](#_13-election-information-queries)
        - [1.3.1. getEpochStakerInfo](#_131-getepochstakerinfo)
        - [1.3.2. getEpochStakerInfoAll](#_132-getepochstakerinfoall)
        - [1.3.3. getEpochLeadersAddrByEpochID](#_133-getepochleadersaddrbyepochid)
        - [1.3.4. getEpochLeadersByEpochID](#_134-getepochleadersbyepochid)
        - [1.3.5. calProbability](#_135-calprobability)
        - [1.3.6. getEpochStakeOut](#_136-getepochstakeout)
        - [1.3.7. getLeaderGroupByEpochID](#_137-getleadergroupbyepochid)
        - [1.3.8. getRandomProposersAddrByEpochID](#_138-getrandomproposersaddrbyepochid)
        - [1.3.9. getRandomProposersByEpochID](#_139-getrandomproposersbyepochid)
        - [1.3.10. getSlStage](#_1310-getslstage)
        - [1.3.11. getRbSignatureCount](#_1311-getrbsignaturecount)
        - [1.3.12. getRbStage](#_1312-getrbstage)
        - [1.3.13. getSlotLeaderByEpochIDAndSlotID](#3_113-getslotleaderbyepochidandslotid)
        - [1.3.14. getStakerInfo](#_1314-getstakerinfo)
        - [1.3.15. getValidRBCnt](#_1315-getvalidrbcnt)
        - [1.3.16. getValidSMACnt](#_1316-getvalidsmacnt)
    - [1.4. Random Number Query](#_14-random-number-query)
        - [1.4.1. getRandom](#_141-getrandom)
    - [1.5. Activity Queries](#_15-activity-queries)
        - [1.5.1. getActivity](#_151-getactivity)
        - [1.5.2. getSlotActivity](#_152-getslotactivity)
        - [1.5.3. getValidatorActivity](#_153-getvalidatoractivity)
    - [1.6. Deprecated API](#_16-deprecated-api)
        - [1.6.1. getBootNodePK](#_161-getbootnodepk)
        - [1.6.2. getIncentiveRunTimes](#_162-getincentiveruntimes)
        - [1.6.3. getRBAddress](#_163-getrbaddress)
        - [1.6.4. getSlotCreateStatusByEpochID](#_164-getslotcreatestatusbyepochid)
        - [1.6.5. getSlotScCallTimesByEpochID](#_165-getslotsccalltimesbyepochid)
        - [1.6.6. getSmaByEpochID](#_166-getsmabyepochid)
        - [1.6.7. getTotalIncentive](#_167-gettotalincentive)
        - [1.6.8. getTotalRemain](#_168-gettotalremain)

<!-- /TOC -->

# 1. PoS-API

## 1.1. Basic Info Queries

### 1.1.1. version
Get version information of POS-API
```
> pos.version()
"1.0"
>
```
### 1.1.2. getPosInfo
Obtain upgrade location information from the POW protocol to the POS protocol
```
> pos.getPosInfo()
{
  firstBlockNumber: 3560000,
  firstEpochId: 18078
}
```
Where `firstBlockNumber` is the block number of the first POS

`firstEpochId` is the Epoch ID under the first POS protocol. In the POW phase, this value is 0.

### 1.1.3. getEpochID
Get current Epoch ID
```
> pos.getEpochID()
18108
```
### 1.1.4. getEpochBlkCnt
Get the number of output blocks of the specified epoch, the input parameter is Epoch ID
```
> pos.getEpochBlkCnt(18107)
13753
```
### 1.1.5. getEpochIDByTime
Epoch ID based on time, enter UTC time seconds, return Epoch ID
```
> Date.now()
1564546408833
> Date.now()/1000
1564546412.857
> pos.getEpochIDByTime(1564546412)
18108
```
### 1.1.6. getEpochIdByBlockNumber
Get the Epoch ID based on the block number
```
> eth.blockNumber
4017608
> pos.getEpochIdByBlockNumber(4017608)
18108
```
### 1.1.7. getSlotID
Get the current Slot ID
```
> pos.getSlotID()
3072
```
### 1.1.8. getSlotCount
Get the number of slots in an epoch
```
> pos.getSlotCount()
17280
```
### 1.1.9. getSlotIDByTime
Calculate the Slot ID based on time, enter the UTC time seconds, and return the Slot ID.
```
> Date.now()
1564546408833
> Date.now()/1000
1564546412.857
> pos.getSlotIDByTime(1564546412)
3042
```
### 1.1.10. getSlotTime
Get the time span of a slot in seconds
```
> pos.getSlotTime()
5
```
### 1.1.11. getChainQuality
Get chain quality information. Enter epoch ID and slot ID, return chain quality value is a thousand points, for example, 770 means 77.0%. Chain quality is based on node ping time and activeness parameters.
```
> pos.getChainQuality(18108,3072)
770
```
### 1.1.12. getLocalPK
Get the public key of the staking account of the local node
```
> pos.getLocalPK()
"04088b71907178ad7392736e7b817f1945364d0798665279f9d829299726828285366a0107a75c53d1e0f90b5251f0e33ab3abf4ef907fe28d0493bfeaa81ba676"
>
```
### 1.1.13. getMaxStableBlkNumber
Get the current maximum stable block number (block which will not roll back)
```
> pos.getMaxStableBlkNumber()
4018017
```
### 1.1.14. getReorgState
Get the current epoch rollback status, enter the epoch id, returns the number of rollbacks and the maximum rollback length
```
> pos.getReorgState(18108)
[0, 0]
>
```
### 1.1.15. getTimeByEpochID
Get the start time of the specified epoch, returns UTC time seconds
```
> pos.getTimeByEpochID(18108)
1564531200
> t=new Date(1564531200000)
<Date Wed, 31 Jul 2019 08:00:00 CST>
>
```
### 1.1.16. getWhiteListConfig
Obtain the configuration information of the Wanchain Foundation controlled nodes, including the effective epochID, the number of controlled nodes, and the starting sequence number.
```
> pos.getWhiteListConfig()
[{
    EpochId: 0,
    WlCount: 26,
    WlIndex: 0
}]
```
### 1.1.17. getWhiteListbyEpochID
Get the list of Wanchain Foundation controlled node public keys for the specified epoch
```
> pos.getWhiteListbyEpochID(18108)
["0x0451cffffa2fb947261efca509564768d909a4fefd450c0e00effc8d7cb848dbd08939e163a6a41bde571f4ae0056b876c2b01c18e1e2d6b7a4745b49f5f5912c0", 
......
"0x04fdb485b566c2ddb40e2f4341b1e5746479a7c45e3d8101b1360b8bdba6206deee520ceecc9e9897e3b05b53e3ffa6fa659bef47c384984c0bc021a843df10847"]
```
## 1.2. Reward Info Queries

### 1.2.1. getEpochIncentivePayDetail
Get the reward information for the specified epoch, enter epochID, return the reward payment details (including RNP reward, EL reward and block reward) for all verification nodes and delegators working at this epoch）
```
>pos.getEpochIncentivePayDetail(18106)
[{
    address: "0xfb3b101776390f993f118cb959f38135c562c52a",
    delegators: [{
        address: "0x19ac9bb112cb2f903fe866b35c5eb59c4278fcbd",
        incentive: "0x71e72f24a7e92afe",
        type: "delegator"
    }],
    incentive: "0x271dbee21dc6d3e17",
    stakeInFromAddr: "0x56664f3b65cc5daf4098ed10b66c4a86e58e21a4",
    type: "validator"
},
......
]
```
### 1.2.2. getEpochIncentiveBlockNumber
Get the block number where incentives are issued in the specified epoch, the input parameter is epochID
```
> pos.getEpochIncentiveBlockNumber(18106)
4003788
```
### 1.2.3. getEpochIncentive
Get the total incentives amount issued in the specified epoch, enter epochID to return the incentives amount in Wei
```
> pos.getEpochIncentive(18106)
"3710904768743286494978"
> web3.fromWin(3710904768743286494978)
"3710.9047687432865"
```
### 1.2.4. getEpochGasPool
Get the total transaction fees for the specified epoch in Wei
```
> pos.getEpochGasPool(18106)
"22306530114000000000"
```
### 1.2.5. getEpochRemain
Get the remaining rewards that have not been issued in the specified epoch due to validator inactivity. This reward will be added to the total rewards for the next 365 epoch cycle.
```
> pos.getEpochRemain(18106)
"3160716829863864189953"
```
### 1.2.6. getIncentivePool
Get the incentives pool sizes of the specified epoch, the return values are the total reward, the foundation reward, and the transaction fee reward
```
> pos.getIncentivePool(18106)
["6871621598607150684931", "6849315068493150684931", "22306530114000000000"]
```


## 1.3. Election Information Queries

### 1.3.1. getEpochStakerInfo
Get the staking weight information of the specified validator of the specified epoch. The input parameters are epochID and validator address.


Where TotalProbability is the total weight value selected for this certifier

The Infors field contains the various sub-items in the total weight. The first sub-item is the validator itself, and the rest is its delegators.

```
> pos.getEpochStakerInfo(18106,'0x17d47c6ac4f72d43420f5e9533b526b2dee626a6')
{
  Addr: "0x17d47c6ac4f72d43420f5e9533b526b2dee626a6",
  FeeRate: 1000,
  Infors: [{
      Addr: "0x17d47c6ac4f72d43420f5e9533b526b2dee626a6",
      Probability: "0x297116712be7b468800000"
  }, {
      Addr: "0x4e6b5f1abdd517739889334df047113bd736c546",
      Probability: "0x849d149d594bdae800000"
  }],
  TotalProbability: "0x31bae7bb017c7217000000"
}
```
### 1.3.2. getEpochStakerInfoAll
Get all the validator node information of the specified epoch, the input parameter is epochID

Individual fields are the same as getEpochStakerInfo

```
>pos.getEpochStakerInfoAll(18106)
[{
    Addr: "0xa36576c856fe69faf1be738252febc3268075619",
    FeeRate: 10000,
    Infors: [{
        Addr: "0xa36576c856fe69faf1be738252febc3268075619",
        Probability: "0x84a079b60afeadbe80000"
    }],
    TotalProbability: "0x84a079b60afeadbe80000"
}, {
    Addr: "0x158bae682e6278a16d09d7c7311074585d38b54d",
    FeeRate: 1,
    Infors: [{
        Addr: "0x158bae682e6278a16d09d7c7311074585d38b54d",
        Probability: "0x29db4e3b8931016a000000"
    }],
    TotalProbability: "0x29db4e3b8931016a000000"
}]
```
### 1.3.3. getEpochLeadersAddrByEpochID
Get the list of epoch leader addresses for the specified epoch, the input parameter is EpochID.
### 1.3.4. getEpochLeadersByEpochID
Get the list of epoch leader public keys of the specified epoch, the input parameter is EpochID
### 1.3.5. calProbability
Calculate the number of election tickets awarded for a given amount of WAN and staking time in Epochs. 
### 1.3.6. getEpochStakeOut
Get amount of stake in WAN withdrawn for the indicated epoch.
```
> pos.getEpochStakeOut(18106)
[{
    address: "0x74b7505ef4ee4a4783f446df8964b6cdd4c61843",
    amount: "0x8f1d5c1cae3740000"
}]
```
### 1.3.7. getLeaderGroupByEpochID
Get the list of EL and RNP addresses and public keys for the specified epoch.

Type is 0 for Epoch Leader, 1 for Random Number Proposer.

The pubBn256 value is 0x for the Wanchain Foundation controlled nodes.

```
pos.getLeaderGroupByEpochID(18106)
[{
    pubBn256: "0x26f35218edefaf8e1547e9a463d14dd884cdc3dfc7e56b26167a50cb038367a10b9e3eaca8fa11624845f3d29f57219661df5b1ae388879815a01f920e838704",
    pubSec256: "0x0459ce8b55d547f24c2c88a4a642a755ca714f5749e5f0e0d8ea5237f8efdb36063c449a8883bc3c36bd263fc1256f3484b33b1598340ab176faecd4499e9bcbba",
    secAddr: "0x882c9c16c05496d7b5374840936aec1af2a16553",
    type: 0
}]
```
### 1.3.8. getRandomProposersAddrByEpochID
Get the address list of Random Number Proposers for the specified epoch
### 1.3.9. getRandomProposersByEpochID
Get the public key 2 list of Random Number Proposer for the specified epoch (public key 2 is used for RNP operations)
### 1.3.10. getSlStage
Obtain the indicated slot's EL work stage, enter slotID as parameter.
```
if slotId <= posconfig.Sma1End {
    return 1
} else if slotId < posconfig.Sma2Start {
    return 2
} else if slotId <= posconfig.Sma2End {
    return 3
} else if slotId < posconfig.Sma3Start {
    return 4
} else if slotId <= posconfig.Sma3End {
    return 5
} else {
    return 6
}
```
### 1.3.11. getRbSignatureCount
Get the number of RNP signatures in the specified epoch, enter epochID and blockNumber, blockNumber is -1 for the latest block
```
> pos.getRbSignatureCount(18106, -1)
15
```
### 1.3.12. getRbStage
Get the RNP working phases of the specified slot, the input parameter is slotID, there are a total of 6 phases
```
RbDkg1Stage
RbDkg1ConfirmStage
RbDkg2Stage
RbDkg2ConfirmStage
RbSignStage
RbSignConfirmStage
```
### 1.3.13. getSlotLeaderByEpochIDAndSlotID
Get the Slot Leader public key of the specified epoch and specified slot
```
> pos.getSlotLeaderByEpochIDAndSlotID(18106,1)
"0484caedf55f668c4cbd966f4aa3c0c1a064e33b1c3ab6c0bc4de7323583893e0fc2cbfe6f4fa3a53f2b57a24f0420b337bcc2f7fa9f9fc4e5e9d95b5c3874360d"
>
```
### 1.3.14. getStakerInfo
Get the validator details for the specified blockNumber

amount：principal stake of validator node

clients: list of delegators

votingPower: the validator's 'tickets' for the lottery for EL and RNP roles, determined by amount of stake and locking time

quitEpoch: The epoch number where delegators will receive their delegation back if the validator quits. Returns 0 when the validator is not quitting.

feeRate: Commission rate (an integer from 0 to 10000, so 500 would be a 5% commission) 

feeRateChangedEpoch: The most recent epoch ID in which feeRate was changed

from: The funding account for the principal stake 

lockEpochs: The current epoch locking period in epochs 

maxFeeRate: Maximum fee rate

nextLockEpochs: The locking period of the next cycle in epochs. When this value is 0, it will exit in the next cycle and the principal will be refunded.

stakingEpoch: The epoch ID of the work starting time of this locking period 

```
> pos.getStakerInfo(eth.blockNumber)
[{
    address: "0xf92ba56ac2506cb97c1d9ce55a54c595e0599ebd",
    amount: 5e+22,
    clients: [{
        address: "0x28f86db797a302b46fa04749faafb1b1c901ff19",
        amount: 100000000000000000000,
        quitEpoch: 0,
        votingPower: 1.002e+23
    }, {
        address: "0xc91e50c0ce32bb024e7e359ae2e829c7f2451e0b",
        amount: 1.248e+21,
        quitEpoch: 0,
        votingPower: 1.250496e+24
    }, {
        address: "0x7ed6135f81453059776ecbf3a838853103f3bf9d",
        amount: 2e+21,
        quitEpoch: 0,
        votingPower: 2.004e+24
    }, {
        address: "0xb3850a2c15c208075197645fc9a4010f8f7634a0",
        amount: 1.11e+22,
        quitEpoch: 0,
        votingPower: 1.11222e+25
    }, {
        address: "0x13944221112c8109be7dcd2adb6d47545dc45be3",
        amount: 1.249e+21,
        quitEpoch: 0,
        votingPower: 1.251498e+24
    }, {
        address: "0x4e6b5f1abdd517739889334df047113bd736c546",
        amount: 2.1e+23,
        quitEpoch: 18109,
        votingPower: 2.1042e+26
    }],
    feeRate: 2000,
    feeRateChangedEpoch: 18088,
    from: "0xf92ba56ac2506cb97c1d9ce55a54c595e0599ebd",
    lockEpochs: 30,
    maxFeeRate: 2000,
    nextLockEpochs: 30,
    partners: [],
    pubBn256: "0x1c466cedd50c33fac011ad4a8f14a177ef5d243e0d7add5c231935f545b30eb80015184d74bc7295b512ffdf9c69824c9db536ae07f1ab14f7eb2eed9a4f1b19",
    pubSec256: "0x041cd717ce3d97ff93d5dcd5f80d78897956dcded35dbaf7c7180bdaff3beb84b900c48b1fbd0c52feaef9aa5e3aae87707cc02eb0a0203b3b6f7911c2fb2bccdf",
    stakingEpoch: 18088,
    votingPower: 5.7e+25
}
```
### 1.3.15. getValidRBCnt

Get the number of RNPs that execute the protocol in the specified epoch
Enter epoch ID, returns the number of RNP nodes which have effectively participated in the DKG1, DKG2, and SIGN stages of random number generation for the specified epoch.

```
> pos.getValidRBCnt(18106)
[14, 14, 15]
```
### 1.3.16. getValidSMACnt
Obtains the number of ELs participating in the POS protocol for the specified epoch, and returns the number of valid participants for SMA1 and SMA2 stages respectively.
 
```
> pos.getValidSMACnt(18106)
[40, 40]
```
## 1.4. Random Number Query

### 1.4.1. getRandom
Query the random number generation result for the specified blockNumber and epoch. If blockNumber is -1, it indicates the latest block.

If the random number does not exist, Error: no random number exists is returned, indicating that the random number of the epoch has not been generated, or because the number of participating RNPs is below the required threshold, the generation fails. The default random number is used when it fails. 

```
> pos.getRandom(18106,-1)
Error: no random number exists
    at web3.js:3145:20
    at web3.js:6381:15
    at web3.js:5083:36
    at <anonymous>:1:1

> pos.getRandom(18107,-1)
"0x7241916d8f2a68937783cc577a373e22d74686a6a36b72937c2cbe3c6b58529c"
>
```


## 1.5. Activity Queries

### 1.5.1. getActivity
Get the activity information of the specified epoch, for historical epochs it is a fixed value, and for the current epoch it will update with the latest current value in real time.

Where epLeader is the epoch leader list of the epoch, and epActivity is whether the epoch leader in the corresponding list completes all EL protocol work.

rpLeader is the list of random number proposers of the epoch, rpActivity shows the activity of the RNPs of the corresponding list, with 1 indicating all work has been completed.

sltLeader is the selected list of exporters, which does not contain controlled nodes. slBlocks is the actual number of outbound blocks for each person in the sltLeader list.

slActivity is the activity of this epoch, which is the total number of produced blocks divided by the total number of slots in the epoch.

slCtrlCount is the number of blocks produced by the Wanchain Foundation controlled nodes in this epoch.

```
> pos.getActivity(18106)
{
  epActivity: [0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 0, 1, 0, 1, 1, 1, 1, 0, 1, 1, 0, 0, 0, 1],
  epLeader: ["0x882c9c16c05496d7b5374840936aec1af2a16553", "0x3628bf135f36c6e26a824ec9152885505f3fbc2a", "0x4add297a1c2eea65e1ab5fd67e79647ecea8f36c", "0x4bf9fd7308d0849a62c3a7dd71c5190e57c28756", "0xb58230a7923a6a1941016aa1682e212def899ed1", "0x1779a2002402319821e05977ad989e1cc0d3fbc3", "0x93c8ea0326ef334bdc3011e74cd1a6d78ce0594d", "0x2bfd98be771eeeb4d69dd8767d200ba58252d925", "0x28c12c7b51860b9d5aec3a0ceb63c6e187c00aac", "0x882c9c16c05496d7b5374840936aec1af2a16553", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xee1ad9c4f9d81f900221e95ee04246b6254b0c6f", "0x6273ce1f6f32e129f295f138d6e4ba6f0e19333e", "0x0b80f69fcb2564479058e4d28592e095828d24aa", "0x9ce4664e9d7346869797b7d9fc8c7a0212d5ff44", "0x2f78203c3161f1139edf2ba4b17b4e430ad2cbfa", "0x17d47c6ac4f72d43420f5e9533b526b2dee626a6", "0x742d898d2ee28a338f03af79c47762a908281a6a", "0xb901829c7e8b7d1de44d8bce086e7a5b0bcc7957", "0x39140deffdbd7c3b2415c29a40e0571365819f57", "0x60528316c553df7cae86d1294ca0d381ebb65cf0", "0x052e421be8e93d6f6c4d3d99defed914920fb3c4", "0x2c72d7a8c02752fcfafbaea5a63c53056cfaf547", "0x3dabf8331afbc553a1e458e37a6c9c819c452d55"],
  rpActivity: [0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 1, 0, 0, 1, 1, 1],
  rpLeader: ["0x20e5203a97b2e08c3dcc22c1c32e0dde3cc41da8", "0xbdada4f58d17ce602cb0d2db2a55c3e4f47e397f", "0xa923ac48439add7124763b3682f4505044c81ae3", "0x94ecbf26582455f5a7c88ab65a5a4ac05f6fe231", "0xdcefae3fdb94815f5d15111b46a5761a39b6ec9d", "0xf92ba56ac2506cb97c1d9ce55a54c595e0599ebd", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xa4ebf5bbb131179b69bbf33319257728cdada5cf", "0x1a95e85e8ffcfd28eb61ee53a542dc98c57b337a", "0x266ddcfdbe3ded75e0e511e6356bca052b221c6b", "0xa4626e2bb450204c4b34bcc7525e585e8f678c0d", "0x533c13658591caa8a188211e73097adea7b94010", "0x0b80f69fcb2564479058e4d28592e095828d24aa", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xa4626e2bb450204c4b34bcc7525e585e8f678c0d", "0xeeb157fdf2a72959f2f8be75ff500cf7a2104fbb", "0x4729672067e1ad8ca7f5770e3273747fe52affad", "0xcf34eb7f491fa7d18ba132938d7208e39da4b509", "0xcd54e0c35b122860d8fe2eb41f2e8e3e79c085ba", "0x28c12c7b51860b9d5aec3a0ceb63c6e187c00aac", "0xb64b60ba915bc16dc71ea59c9950c1538dcead9c", "0x36fad9acaf51a13527375b1ffc3d5a749153efdb", "0xdfd7aa554653ca236c197ad746edc2954ca172df", "0x4add297a1c2eea65e1ab5fd67e79647ecea8f36c", "0xc7afae3c9e99af27fe3eaa10f6ec73cd2dbe003b"],
  slActivity: 0.794675925925926,
  slBlocks: [331, 1338, 666, 338, 338, 323, 341, 364, 349, 368],
  slCtrlCount: 8976,
  sltLeader: ["0xfb3b101776390f993f118cb959f38135c562c52a", "0xee1ad9c4f9d81f900221e95ee04246b6254b0c6f", "0x026e37c00451428027ebbbc2c81dce7e280ae97d", "0x1a95e85e8ffcfd28eb61ee53a542dc98c57b337a", "0xc7afae3c9e99af27fe3eaa10f6ec73cd2dbe003b", "0x533c13658591caa8a188211e73097adea7b94010", "0x4bf9fd7308d0849a62c3a7dd71c5190e57c28756", "0xda8fa1aee77709d37f59fb96afd4cf10ccaeb6ce", "0xb019a99f0653973ddb2d983a26e0970587d08447", "0x2f78203c3161f1139edf2ba4b17b4e430ad2cbfa"]
}
>
```
### 1.5.2. getSlotActivity
Get the activity for the blocks produced in the spefified epoch

sltLeader is the list of selected block producers, which does not contain Wanchain Foundation controlled nodes. slBlocks is the actual number of blocks for each node in the sltLeader list.

slActivity is the activity of this epoch, which is the total number of outbound blocks divided by the total number of slots in the epoch.

slCtrlCount The number of blocks produced by the Wanchain Foundation controlled nodes in this epoch.

```
> pos.getSlotActivity(18106)
{
  slActivity: 0.794675925925926,
  slBlocks: [338, 364, 349, 341, 331, 368, 323, 1338, 666, 338],
  slCtrlCount: 8976,
  sltLeader: ["0x1a95e85e8ffcfd28eb61ee53a542dc98c57b337a", "0xda8fa1aee77709d37f59fb96afd4cf10ccaeb6ce", "0xb019a99f0653973ddb2d983a26e0970587d08447", "0x4bf9fd7308d0849a62c3a7dd71c5190e57c28756", "0xfb3b101776390f993f118cb959f38135c562c52a", "0x2f78203c3161f1139edf2ba4b17b4e430ad2cbfa", "0x533c13658591caa8a188211e73097adea7b94010", "0xee1ad9c4f9d81f900221e95ee04246b6254b0c6f", "0x026e37c00451428027ebbbc2c81dce7e280ae97d", "0xc7afae3c9e99af27fe3eaa10f6ec73cd2dbe003b"]
}
```
### 1.5.3. getValidatorActivity

Get the activity information of the specified Epoch's EL and RNP, for current epochs or future epochs returns null

Where epLeader is the epoch leader list of the epoch, and epActivity is whether the epoch leader in the corresponding list completes all required EL protocol work.

rpLeader is the list of random number proposers of the epoch, rpActivity shows whether the corresponding RNP has completed all work required by the protocol.

```
> pos.getValidatorActivity(18106)
{
  epActivity: [0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 0, 1, 0, 1, 1, 1, 1, 0, 1, 1, 0, 0, 0, 1],
  epLeader: ["0x882c9c16c05496d7b5374840936aec1af2a16553", "0x3628bf135f36c6e26a824ec9152885505f3fbc2a", "0x4add297a1c2eea65e1ab5fd67e79647ecea8f36c", "0x4bf9fd7308d0849a62c3a7dd71c5190e57c28756", "0xb58230a7923a6a1941016aa1682e212def899ed1", "0x1779a2002402319821e05977ad989e1cc0d3fbc3", "0x93c8ea0326ef334bdc3011e74cd1a6d78ce0594d", "0x2bfd98be771eeeb4d69dd8767d200ba58252d925", "0x28c12c7b51860b9d5aec3a0ceb63c6e187c00aac", "0x882c9c16c05496d7b5374840936aec1af2a16553", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xee1ad9c4f9d81f900221e95ee04246b6254b0c6f", "0x6273ce1f6f32e129f295f138d6e4ba6f0e19333e", "0x0b80f69fcb2564479058e4d28592e095828d24aa", "0x9ce4664e9d7346869797b7d9fc8c7a0212d5ff44", "0x2f78203c3161f1139edf2ba4b17b4e430ad2cbfa", "0x17d47c6ac4f72d43420f5e9533b526b2dee626a6", "0x742d898d2ee28a338f03af79c47762a908281a6a", "0xb901829c7e8b7d1de44d8bce086e7a5b0bcc7957", "0x39140deffdbd7c3b2415c29a40e0571365819f57", "0x60528316c553df7cae86d1294ca0d381ebb65cf0", "0x052e421be8e93d6f6c4d3d99defed914920fb3c4", "0x2c72d7a8c02752fcfafbaea5a63c53056cfaf547", "0x3dabf8331afbc553a1e458e37a6c9c819c452d55"],
  rpActivity: [0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 1, 0, 0, 1, 1, 1],
  rpLeader: ["0x20e5203a97b2e08c3dcc22c1c32e0dde3cc41da8", "0xbdada4f58d17ce602cb0d2db2a55c3e4f47e397f", "0xa923ac48439add7124763b3682f4505044c81ae3", "0x94ecbf26582455f5a7c88ab65a5a4ac05f6fe231", "0xdcefae3fdb94815f5d15111b46a5761a39b6ec9d", "0xf92ba56ac2506cb97c1d9ce55a54c595e0599ebd", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xa4ebf5bbb131179b69bbf33319257728cdada5cf", "0x1a95e85e8ffcfd28eb61ee53a542dc98c57b337a", "0x266ddcfdbe3ded75e0e511e6356bca052b221c6b", "0xa4626e2bb450204c4b34bcc7525e585e8f678c0d", "0x533c13658591caa8a188211e73097adea7b94010", "0x0b80f69fcb2564479058e4d28592e095828d24aa", "0x1b7740df685f9d34773d5a2aba6ab3a2c1407f40", "0xa4626e2bb450204c4b34bcc7525e585e8f678c0d", "0xeeb157fdf2a72959f2f8be75ff500cf7a2104fbb", "0x4729672067e1ad8ca7f5770e3273747fe52affad", "0xcf34eb7f491fa7d18ba132938d7208e39da4b509", "0xcd54e0c35b122860d8fe2eb41f2e8e3e79c085ba", "0x28c12c7b51860b9d5aec3a0ceb63c6e187c00aac", "0xb64b60ba915bc16dc71ea59c9950c1538dcead9c", "0x36fad9acaf51a13527375b1ffc3d5a749153efdb", "0xdfd7aa554653ca236c197ad746edc2954ca172df", "0x4add297a1c2eea65e1ab5fd67e79647ecea8f36c", "0xc7afae3c9e99af27fe3eaa10f6ec73cd2dbe003b"]
}
```

## 1.6. Deprecated API

The following API interfaces have been deprecated and will be removed in subsequent releases.

### 1.6.1. getBootNodePK
### 1.6.2. getIncentiveRunTimes
### 1.6.3. getRBAddress
### 1.6.4. getSlotCreateStatusByEpochID
### 1.6.5. getSlotScCallTimesByEpochID
### 1.6.6. getSmaByEpochID
### 1.6.7. getTotalIncentive
### 1.6.8. getTotalRemain
