# Staking FAQ

1. Can delegators change delegation to different validators without unbonding first? Since unbond process takes one epoch now. 
> In current version, delegators will need to unbond first before switching validators. And unbond process takes 2-3 epochs now. 

1. How validators can monitor that if their nodes are selected as among 49 candidates in current epoch, but their node is not participating in consensus process since, for now, Pos.getActivity(epoch) only shows the previous epoch, current epoch will show all as 0? 
> They can use pos.getLeaderGroupByEpochID(epochID)  API function to get selected leaders in next epoch after 4:00 UTC. See [instructions here](https://www.explorewanchain.org/#/staking/pos-api-manual-en?id=_137-getleadergroupbyepochid). And yes, the pos.getActivity(epoch) is only used for checking the old epoch’s activity. 

1. Sometimes a server reboot is required(maintenance). Can we reboot without losing any reward if we do this when the node is not selected for any role?
> Yes, you can reboot your validator node when it is not selected for any role. And you can reboot it after 23:00 UTC when you are selected but have completed all the work in the epoch.

1. When you release new GWAN version and validator operators have to update, does this mean we will lose rewards for the epoch just because we had to update?
> Validators can update to a new gwan version before the fork block number, and update after 23:00 UTC to avoid losing rewards. If the new version is a hard fork version, anybody who doesn’t update gwan will lose their rewards. But we will not have many versions like this.

1. What is the threshold for the "offline" status for nodes? For example, if the internet disconnects for 5 seconds is it considered being down (and lose reward)?
> No. 5 seconds disconnect will not affect online status. Only if the validator is selected and doesn’t do its work of EL or RNP will be considered not active in the current epoch. The important work times are 00:00, 4:00, 8:00, 12:00... every 4 hours in UTC time.  

  <p id="node-switch"></p>

1. Will it be possible to switch an active node from one server to another (e.g. AWS --> GCloud)?  
> Yes, here are the instructions:
> 1. Set up the new server
> 2. Install Docker manually
> 3. Create folder at ~/.wanchain/keystore
> 4. Copy/paste the content of the JSON keystore content you got when first starting the validator node into a "keystore" file and put it into the folder created in step 3
> 5. Run updateMainnetValidator.sh with the name, address and password from the validator node first created.  
>
> **Note:** In order not to lose staking rewards, take care about when in the protocol timeline you perform the switch. If your node has not been selected, you can do it anytime. If you are selected as Epoch Leader or Random Number Proposer, you should do it after 23:00 UTC and before 00:00 UTC, and if have been selected as Slot Leader, you should wait for next day.

1. What does "Reorg len" mean on testnet.wanstats.io? 
> When the network quality is poor, the blockchain will produce a temporary soft fork, and then reach agreement through fork rollback. Reorg len represents the maximum rollback length of the current epoch. 

1. I successfully deployed a contract on Ethereum. Can I directly deploy it on Wanchain with the previously compiled files?  
> Yes, the bytecode is the same.

1. I deployed a contract on the test chain, but I could not call the contract, what is the reason?  
> Please change Solidity compiler to 0.5.1 or above.

1. My validator node has been running for +8 days now, but it seems that the 'Total reward' is still 0. Is there something in the configuration that I forgot to do?
> Please update GWAN to the most recent version.

1. What happens if I register the same pk1/pk2 from 2 addresses? 
> The second register transaction will fail.
 
1. The node syncing in GWAN is very slow.
> Update to the newest version of GWAN.

1. Is it required to keep a copy of the keystore to receive rewards for the PoS Beta Testnet?
>Yes, please keep it. If you lose it, please get in touch with us at info@wanchain.org.

1. How can I get the JSON keystore if I used the "Extended Setup" method? 
> The keystore file is stored at ~/.wanchain/testnet/keystore by default.

1. How can I update the display name, logo, and website of my node?
> Please use this [form](https://forms.office.com/Pages/ResponsePage.aspx?id=VPnN3XSIEEqLYwFUDjqIlhDN00eQ8opLu9Rbjur15g5UOTVCNFoxQ0dCRUNFTFQzTTVBVFFVMjI2OS4u). You may email [info@wanchain.org](info@wanchain.org) if you experience any issues with the form.

1. What is benefit if I have more than 25 peers? 
> There is no benefit.  The max peers defaults to 25, but may be modified.
  
1. Why do we need 256GB of disk space for a validator node? 
> This takes into account long term growth. 40GB should be sufficient for the first year.

1. For the final release, will we be able to register from WAN Wallet so that the keystore file or mnemonic phrase never leaves the machine? 
> Yes this will be available when PoS launches on the mainnet.

1. I have my validator node's keystore, how can I import it to the Wan Wallet? 
> The option is in the Wan Wallet menu under Wan Wallet > Developer > Assets > Wanchain > Import Keystore File.

1. If a deployed a smart contract before the switch to POS, will it still be available after the switch on the mainnet? 
> Yes, all smart contracts deployed before POS is rolled out on the mainnet will be unchanged by the rollout.

1.  Is ok that some nodes did not receive any reward in last epoch? 
> This is normal. A total of 49 slots are open for nodes to be chosen to participate within each epoch, and the same node may potentially fill multiple slots, so at most 49 nodes (but often less than 49 nodes) will be chosen to participate and receive rewards each epoch. The process is probabilistic with the chance to be chosen going up with the amount of stake and locking time. 

1. I can see my node on http://testnet.wanstats.io/ but not on http://testnet.wanscan.org/vlds. Does the latter happen later? 
> Yes, there can be a delay of several minutes. Also please verify your register transaction’s status at http://testnet.wanscan.org/. Same for mainnet. 

1. What are some other options besides AWS for running a node?
> You can also try [Google Cloud](https://cloud.google.com/compute/), or other cloud computing providers.

1. When registering my validator node through MyWanWallet.io, I keep getting a notice about insufficient funds. What should I do? Does my gas have to be a certain amount? 
> Please wait for the gasLimit to be automatically estimated before making the transaction. 

1. Is a fixed IP needed for Wanchain Validator nodes? 
> It is not needed.

1. Can I use Ledger address to register as validator node? 
> Ledger can be used from the stake funding account to register (lock WAN for staking), but can not be used for node operations.
