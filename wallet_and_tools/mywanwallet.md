# “Partner-in” Now Supports Hardware Wallets for Both Storeman & POS Nodes!


The “Partner-in” model allows for multiple node operators / addresses to jointly operate a node and receive delegations & rewards as a group


## 0. Preliminary Notes

As a Storeman node operator, you should understand the following:

* Partner-in is non-custodial, each partner’s fund will always be returned to the original partner when the node exits
* If the Storeman is dishonest, all partners will be slashed
* The leader partner receives all network rewards, and distribution happens offline (assumes the joining partners know and trust the leader partner to distribute rewards)
* A node can have 5 partners at most
* Each partner must have a minimum of 10,000 WAN

## Step by Step Instructions

_If you don’t have a Ledger or Trezor hardware wallet, please refer to “Wanchain Offline Wallet Partner In Usage Method” ._

**1\. Access contract page of the MyWanWallet website**

Access: [https://mywanwallet.com/#contracts](https://mywanwallet.com/#contracts)

**2\. Verify that you are using the correct network (Mainnet / Testnet)**

At the top right of the page, confirm that you have selected Network WAN Mainnet (mywanwallet.com):

![](https://miro.medium.com/max/693/1*neqcmIw-4d7mOjpmFvYE-w.png)

**3\. Enter the Storeman contract address in Contract Address**

Enter the OSM contract address of mainnet in Contract Address: 0x1e7450d5D17338A348c5438546F0B4d0a5FBEAb6

**4\. Enter ABI / JSON Interface information**

Copy and paste the ABI / JSON Interface.

[Download ABI](https://github.com/wanchain/explore-wanchain/blob/master/_media/storeman_contract_ABI.json)

**5\. Click the “Access” button**

![](https://miro.medium.com/max/693/1*phkKIkm1Ffkpe-qvdwCGxA.png)

**6\. In the Read / Write Contract drop-down box that appears, select “partIn”**

![](https://miro.medium.com/max/693/1*3kfss9pY1r9BV9GAZCKWNw.png)

**7\. Enter the Work Address of the node you want to participate in**

![](https://miro.medium.com/max/693/1*ccciQQDNg-vrkm8x6TqG9w.png)

**8\. Choose your hardware wallet and connect**

First select your hardware wallet, and click the connect button;

![](https://miro.medium.com/max/693/1*NUjER6zehDKZmQXEdSR5uA.png)

Choose your participating address and click “Unlock your Wallet”;

![](https://miro.medium.com/max/693/1*1v5SI_iiNH8uwsB5EPZZsQ.png)

After connecting to the wallet and selecting the address successfully, click the “WRITE” button;

**9\. Enter the number of WAN you want to partner-in and confirm**

Enter the number of WAN (at least 10,000) you want to partner in with, and after the Gas Limit is automatically refreshed (wait until it does not show -1), click the “Generate Transaction” button. Then confirm the authorized transaction on the hardware wallet.

![](https://miro.medium.com/max/693/1*cr1CNPgSxmeOflo_u8mcMg.png)

After the transaction signature information is generated, click “Yes, I am sure! Make transaction.”

![](https://miro.medium.com/max/693/1*MxV8e0NlVBrnLeXVj_wUSw.png)

At this time, at the bottom of the page, there will be a prompt that the transaction has been broadcast online.

![](https://miro.medium.com/max/693/1*XWL3hAlfM9-o-IF8NfA6rw.png)

**10\. View the results on the Wanscan browser**

Open the [Storeman group list pag](https://www.wanscan.org/storemangroups)e and click onthe Storeman group that is being joined, find the node you are participating in, and click its name or address to enter, there you can check whether your operation was successful.

**11\. partOut & partClaim**

**Please note:** PartOut can only be carried out after the selection of the Storeman Group is completed, and partClaim can be carried out after disbandment.

The process is the same as steps 1~10 above, **except that in step 6, the selection is no longer “partIn”, but “partOut” or “partClaim”.**

**In step 9, the “Amount to Send…” input value must be 0, and 1000000 in “Gas Limit”.**

![](https://miro.medium.com/max/693/1*BsoXTLZAvo_jgZpT9CG1Fg.png)

