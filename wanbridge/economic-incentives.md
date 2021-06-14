# Chapter 2: Storeman Economic Incentives & Slashing


![](https://miro.medium.com/max/2732/0*FYVl6eby6Sej3tUX.png)

## Introduction

Wanchain 5.0’s economic incentives serve two primary purposes

First, community members are rewarded to act as Storeman nodes building bridges to provide the cross-chain functionality. Second, malicious behaviors are punished by slashing bonded stake.

**CHANGES FROM PREVIOUSLY ANNOUNCED REWARDS MECHANISM:**

Before digging into the details of the reward and slashing mechanism, please note that several previously announced incentives details have been changed:

1.  The Stake to Delegation ratio has been changed from 1:5 to 1:1 (This is a temporary security measure to limit total stake locked in the system during the first couple MPC cycles. By the end of the 1st or 2nd MPC cycle it will be upgraded as long as no security issues have come up.)
2.  The MPC cycle length has been changed from 3 months to 30 days
3.  The delegation fee has been modified from 5% to 10%
4.  Minimum stake for a Storeman node is 10k WAN

## Rewards

The basic principle of the Storeman rewards mechanism is that Storeman operators expend resources and take risks in order to ensure the smooth and secure operation of cross-chain transactions. Delegators contribute stake to storeman nodes, and are thus also rewarded.

### Overall design

*   No cross-chain service fee (temporarily subsidized by Wanchain Foundation)
*   Incentive paid to cross-chain Storeman Node operators who run nodes
*   Incentive paid to delegators who contribute stake to Storeman nodes
*   Total Storeman reward is limited with a **hard cap** to ensure that the high rate of return doesn’t cause too large an amount of funds to move away from Proof of Stake

The total reward of the Storeman system is defined by this formula (this is the sum of the rewards paid out to ALL storeman from all bridges combined):

> r₁ = r₂ × **α**

`r1` denotes reward rate of PoS consensus, `r2` denotes reward rate of crosschain, and `α`denotes zoom coefficient. In the initial stage, we set `α=1.5`, which means the average reward rate of crosschain is 1.5x that of PoS consensus. At present, `r1=7.67%`, so we have `r2=11.5%`.

Second, to achieve a balance between cross-chain reward and PoS consensus reward, we set a hard cap for cross-chain daily reward as

> **HardCap = PoSDR**

`HardCap` is the maximum daily rewards for the Storeman system, and `PoSDR`denotes PoS dail rewards. At present, `HardCap=6027 WAN`.

Assuming the total deposit for crosschain is `w`, then crosschain daily reward `CDR`is computed as

![](https://miro.medium.com/max/641/0*K25657uhzNo7Xg-U.png)

From the above formula we know, as `w`increases, `CDR`grows linearly. When it

reaches 19.1 M, `CDR`equals 6027 WAN and remains unchanged.

![](https://miro.medium.com/max/875/0*ybXxhQPbv3rShfhs.png)

The cross-chain reward rate `r2`is 1.5 times PoS consensus reward rate `r1`before `CDR`reaches hard cap. When `CDR`reaches the hard cap, `r2`decreases linearly as `w`grows. Finally, `r1=r2`, when `w=28.6M WAN`.

![](https://miro.medium.com/max/875/0*NAu4fqivxowjRuKt.png)

In summary, the cross-chain reward rate is higher than the PoS consensus reward rate in the initial stage, which encourages the development of the cross-chain ecosystem. As cross-chain deposits grow, the cross-chain reward rate decreases due to the hard cap. An equilibrium will be reached when the cross-chain and PoS reward rates are equal.

### Reward division between Storeman and delegators

In Wanchain 5.0, cross-chain bridges are built and run by groups of Storeman nodes. Storeman operators stake a security deposit in to ensure honest behavior. Delegators may contribute additional stake to Storeman nodes in order to increase the cross-chain asset transfer limits and share in network reward.s

As described above, `r2`is the crosschain reward rate, which is the average of the Storeman’s reward and thedelegator’s reward. As for reward division, Storeman operators earn more due to node operation costs.

`w1`is the Storeman node deposit, `w2`denotes the deposit of delegators, `Fr` denotes the delegation fee rate, and `μ`denotes the weight. Storeman daily reward(`CDRs`) and delegators’ daily reward(`CDRd`) are calculated as

![](https://miro.medium.com/max/875/0*iWipdAbKiCdxIyW9.png)

Storeman’s reward rate `rs`and delegators’ reward rate `rd`are calculated as

![](https://miro.medium.com/max/875/0*wgW9MqtlqtS8DfXb.png)

Assuming w1=2M, w2=10M, Fr=5%, μ=1.5, then we know CDR=3780, rs=18.57%, rd=10.08%

![](https://miro.medium.com/max/875/0*GqaDDrJVAWan9qi7.png)

### Activeness Index of Storeman Nodes


To evaluate the activeness of Storeman Pi’s participation in the cross-chain process, the activeness index is defined as:

![](https://miro.medium.com/max/156/0*ngPiKdfKcXv8X0CZ.png)

`n` denotes the total number of cross-chain events in Storeman Pi’s work cycle, `m`denotes the number of crosschain events which Pi participates in.

Besides, we set a threshold `τ`for Storeman’s activeness index. Storeman will not get reward if its activeness index is below `τ`. Assuming Storeman Pi has a deposit of `ws`, then its reward `R`is calculated as

![](https://miro.medium.com/max/596/0*wwQtCTv1aNXc6YV9.png)

## Slashing


### Overall design


To ensure security and reliability, malicious behaviors will be punished by the slashing of stake.

The slashing mechanism detects Storeman’s malicious behaviors in a decentralized way without the need of any trusted third party. Specifically, in the keygen stage, Storeman nodes exchange data with each other on chain. Invalid data will be detected by a challenge / response process, which takes the on-chain data as input. In the signing stage, a enhanced version of Shamir’s secret sharing is used with the inclusion of Feldman’s VSS protocol. Any Storeman node is able to verify the validity of the received data. The invalid data will be uploaded to the smart contract to trigger the slashing process. In summary, the detection of malicious behavior is based on on-chain data and smart contracts. So it is publicly verifiable and ensures the correctness and fairness of theslashing mechanism.

### Malicious behaviors and the corresponding slashing methods

![](https://miro.medium.com/max/875/1*rd61ahGal_dMw63DT2rYeQ.png)

