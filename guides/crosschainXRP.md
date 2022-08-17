# How to complete a crosschain transaction (XRP)

An in-depth guide outlining how to complete an XRP crosschain transaction using both the [Wanchain Desktop Wallet](https://www.wanchain.org/wanwallet) and the [WanBridge web portal](https://bridge.wanchain.org/#/).

![](https://miro.medium.com/max/1400/1*zqHwN3qPpuK72sG4LArnmw.jpeg)

This guide will demonstrate four separate crosschain transactions:

1. $XRP from Wanchain to XRP Ledger using the [Wanchain Desktop Wallet](https://www.wanchain.org/wanwallet)
2. $XRP from XRP Ledger to Wanchain using the [Wanchain Desktop Wallet](https://www.wanchain.org/wanwallet)
3. $XRP from Wanchain to XRP Ledger using the [WanBridge web portal](https://bridge.wanchain.org/#/) with Metamask
4. $XRP from XRP Ledger to Wanchain using the [WanBridge web portal](https://bridge.wanchain.org/#/)

> **Note:** XRP Ledger requires a 10 XRP wallet minimum balance, this means that once you send XRP to your address, it will “lock” 10 XRP as a minimum reserve. Read more about it here: https://xrpl.org/reserves.html.

## Crosschain transactions using the Wanchain Desktop Wallet

### $XRP crosschain transaction from Wanchain to XRP Ledger

#### Step 1: Enable wanXRP and XRP on the Wanchain Desktop Wallet.

Navigate to **Wallet** → **More Tokens**.

![](https://miro.medium.com/max/1400/1*agBGgWP3CcVY2FmvYSx0Ag.png)

Scroll down until you see **XRP**. Then, click the stars next to wanXRP and XRP. As in the screenshot below.

![](https://miro.medium.com/max/1400/1*bmb3MUCfEbU-VV587w3Z6g.png)

$XRP and $wanXRP wallets are now enabled and appear in your portfolio overview.

![](https://miro.medium.com/max/1400/1*6j33H8DngCRAOZXMORl30Q.png)

#### Step 2: Enabling XRP crosschain functionality.

Navigate to **Cross Chain** → **More Tokens**.

![](https://miro.medium.com/max/1400/1*rzgg_WC4SJrmRxlop42fUg.png)

Scroll down until you see **XRP**. Then, click the star next to **XRPL <-> Wanchain**. As in the screenshot below.

![](https://miro.medium.com/max/1400/1*wqiIrRHiAoOF-9ctd5wYKQ.png)

#### Step 3: Initiate a crosschain transaction to move your $XRP from Wanchain to XRP Ledger.

Navigate to **Cross Chain → XRP → XRPL <-> Wanchain**.

![](https://miro.medium.com/max/1400/1*-0CEZ87aC2dzSsPkzFjLHw.png)

Since you are moving $XRP from Wanchain to XRP Ledger, click “**Convert**” next to your wanXRP balance, as in the screenshot below. $XRP on Wanchain is called $wanXRP.

![](https://miro.medium.com/max/1400/1*ubdfxsxZZmIc-55Z1LMmgw.png)

Select which of your $XRP wallets you would like to receive the $XRP on XRP Ledger, enter the amount of $wanXRP to convert, then click “**Next**”. Optionally, you can select “**Send Everything**” to move your entire $wanXRP balance to XRP Ledger.

![](https://miro.medium.com/max/1400/1*dknzX6fEN4nCc7g7avbxaA.png)

Confirm that all the details are correct then click “**Send**”. This will initiate the crosschain transaction.

![](https://miro.medium.com/max/1400/1*Wv2L_-4X7eH4bq1MMydFhA.png)

#### Step 4: Wait for your crosschain transaction to complete. It is now processing.

While your crosschain transaction is processing, the status will change three times:

* Lock Request Sent — A lock request has been sent to Wanchain’s bridge nodes.
* Locked — Your wanXRP is now locked with Wanchain’s bridge nodes.
* Success — Your crosschain transaction is now complete.

> **Note:** The speed of the crosschain transaction is entirely dependent on the networks involved. Transactions involving slower networks like Bitcoin or Ethereum may take several minutes or more to complete.

![](https://miro.medium.com/max/1400/1*fqyGAUbScUJcjV2tthPyZA.png)

While your crosschain transaction is processing, you can click the status to view more detailed information.

![](https://miro.medium.com/max/1400/1*cooESbLAKfX6oIjvNnEToA.png)

#### Step 5: Confirm the receipt of your funds. Your crosschain transaction is now complete!

Once your transaction is complete, you’ll see your XRP balance update, and the crosschain transaction status change to “**Success**”.

![](https://miro.medium.com/max/1400/1*up6Exu_qy2eLUR7JXeAAFg.png)

### $XRP crosschain transaction from XRP Ledger to Wanchain

#### Step 1: Initiate a crosschain transaction to move your $XRP from XRP Ledger to Wanchain.

Navigate to **Cross Chain** → **XRP** → **XRPL <-> Wanchain**

![](https://miro.medium.com/max/1400/1*AET-2CtvIjThnLeqfGHC_g.png)

Since you are moving $XRP from XRP Ledger to Wanchain, click “**Convert**” near your XRP balance, as in the screenshot below.

![](https://miro.medium.com/max/1400/1*TnBLv7RTc3KWYGSE-G8LxQ.png)

Select which of your $WAN wallets you would like to receive the $wanXRP on Wanchain, enter the amount of $XRP to convert, then click “**Next**”. Optionally, you can select “**Send Everything**” to move your entire $XRP balance to Wanchain.

![](https://miro.medium.com/max/1400/1*l4xt6kSLgx4AE0rmUV8T8g.png)

Confirm that all the details are correct then click “**Send**”. This will initiate the crosschain transaction.

![](https://miro.medium.com/max/1400/1*xmNNfuxLP6Jw4ptmDHd1Lw.png)

#### Step 2: Wait for your crosschain transaction to complete. It is now processing.

While your crosschain transaction is processing, the status will change three times:

* Lock Request Sent — A lock request has been sent to Wanchain’s bridge nodes.
* Locked — Your XRP is now locked with Wanchain’s bridge nodes.
* Success — Your crosschain transaction is now complete.

> **Note:** The speed of the crosschain transaction is entirely dependent on the networks involved. Transactions involving slower networks like Bitcoin or Ethereum may take several minutes or more to complete.
> You’ll also notice ~10 XRP has been “locked” as the XRP wallet minimum balance as described at the beginning of this guide.

![](https://miro.medium.com/max/1400/1*xh1iY2dbY4daQAThVkj_LQ.png)

While your crosschain transaction is processing, you can click the status to view more detailed information as we did before.

![](https://miro.medium.com/max/1400/1*WNRdRx1ggI44MTJ-z8gzWQ.png)

#### Step 3: Confirm the receipt of your funds. Your crosschain transaction is complete!

Once your crosschain transaction is complete, you’ll see your $XRP balance on XRP Ledger update, and the crosschain transaction status change to “**Success**”.

![](https://miro.medium.com/max/1400/1*8puk_a_0CaRhyj7UaZkcoQ.png)

## Crosschain transactions using the WanBridge web portal

### $XRP crosschain transaction from Wanchain to XRP Ledger

#### Step 1: Make sure you have the appropriate wallets installed.

Before completing decentralised crosschain transactions using the [WanBridge web portal](https://bridge.wanchain.org/#/), you need to ensure you have access to the correct wallet(s). You must have wallets for each network involved in the crosschain transaction. [Metamask](https://metamask.io/) is a fantastic wallet that grants you access to any EVM-compatible blockchain networks.

[Download Metamask here](https://metamask.io/).

#### Step 2: Visit the WanBridge web portal and connect your wallet.

Click “**Connect to Wallet**”.

![](https://miro.medium.com/max/1400/1*7_J4F9qVAvFgyJVfsuaqnw.png)

Click “**Metamask**”.

![](https://miro.medium.com/max/1400/1*H5aze5TUcFOPq9dz2ldEPw.png)

If this is your first time using the [WanBridge web portal](https://bridge.wanchain.org/#/), you will first need to give permission to connect your wallet. Follow the MetaMask prompts by clicking “**Next**” then “**Connect**” as instructed.

![](https://miro.medium.com/max/1400/1*aJNQvz8JbkgdoPkLnZ3PLQ.png)

![](https://miro.medium.com/max/1400/1*_L10ovSswTMhvuiTD3ppjA.png)

#### Step 3: Initiate a crosschain transaction to move your $XRP from Wanchain to XRP Ledger.

Select “**XRP**” from the drop-down menu. Then, choose “**Wanchain**” and “**XRP Ledger**” as your _From_ and _To_ networks, respectively. Finally, input your destination address in the “**Recipient**” field as well as the amount of $XRP you want to send crosschain. Click “**Next**”.

![](https://miro.medium.com/max/1400/1*AGUDxOcGL2s7UrrsET1xQg.png)

Confirm that the “**Recipient**” address does not belong to a centralised exchange then click “**Confirm**”.

![](https://miro.medium.com/max/1400/1*-ZuML0cL5I6I9ZVGUWE5fA.png)

Confirm that all the details are correct then click “**Confirm**”.

![](https://miro.medium.com/max/1400/1*SCTbdVECtOeGsrnzgopR7Q.png)

Confirm the transaction by clicking “**Confirm**” in the MetaMask pop-up window.

![](https://miro.medium.com/max/1400/1*WUEi_u0oJES4McPvlyxPPw.png)

#### Step 4: Wait for your crosschain transaction to complete. It is now processing.

While your crosschain transaction is processing, the status will change three times:

* Processing (1/2)
* Processing (2/2)
* Success

> **Note:** The speed of the crosschain transaction is entirely dependent on the networks involved. Transactions involving slower networks like Bitcoin or Ethereum may take several minutes or more to complete.

![](https://miro.medium.com/max/1400/1*x6VYRL_KALiV6-MO7qIZhw.png)

#### Step 5: Confirm the receipt of your funds. Your crosschain transaction is complete!

Once your crosschain transaction is complete, you’ll see your $XRP balance on your XRP Address address, and the crosschain transaction status change to “**Success**”.

### $XRP crosschain transaction from XRP Ledger to Wanchain

#### Step 1: Make sure you have the appropriate wallets installed.

Before completing decentralised crosschain transactions using the [WanBridge web portal](https://bridge.wanchain.org/#/), you need to ensure you have access to the correct wallet(s). You must have wallets for each network involved in the crosschain transaction. When transferring from networks that do not support native smart contracts, you will be instructed to manually send a transaction to initiate the crosschain transaction. It is highly recommended to only use a wallet that you own and control.

#### Step 2: Visit the WanBridge web portal.

![](https://miro.medium.com/max/1400/1*ecie2iqfLfD3niiNjMjZ-Q.png)

#### Step 3: Initiate a crosschain transaction to move your $XRP from XRP Ledger to Wanchain.

Select “**XRP**” from the drop-down menu. Then, choose “**XRP Ledger**” and “**Wanchain**” as your _From_ and _To_ networks, respectively. Finally, input your destination address in the “**Recipient**” field as well as the amount of $XRP you want to send crosschain. Click “**Next**”.

![](https://miro.medium.com/max/1400/1*PaDusN5TUdS-Ot22J1s1Sw.png)

Confirm that the “**Recipient**” address does not belong to a centralised exchange then click “**Confirm**”.

![](https://miro.medium.com/max/1400/1*oF1aOX4o43CDvCHe9Z5dBA.png)

Confirm that all the details are correct then click “**Confirm**”.

![](https://miro.medium.com/max/1400/1*vx52M8lc58fesnn9thwHTQ.png)

Read the warning and click "**Confirm**".

![](https://miro.medium.com/max/1400/1*n7ZiuYpNihE9-rRbF3Dezg.png)

#### Step 4: Manually send your $XRP to the One-time Address.

Copy the One-time Address and manually transfer the listed amount of $XRP using the XRP wallet of your choice. It is highly recommended to use a XRP wallet that you own and control.

> **Note:** Be sure to send the correct amount of $XRP, as indicated. Send the entire amount as ONE transaction.

![](https://miro.medium.com/max/1400/1*A8hFZFtCe-2RnLFiwf3K6A.png)

Read the warning and click “**Confirm**”.

![](https://miro.medium.com/max/1400/1*h_NuvpeLfJblNYrv-vbVAw.png)

#### Step 5: Wait for your crosschain transaction to complete. It is now processing.

While your crosschain transaction is processing, the status will change three times:

* Processing (1/2)
* Processing (2/2)
* Success

> **Note:** The speed of the crosschain transaction is entirely dependent on the networks involved. Transactions involving slower networks like Bitcoin or Ethereum may take several minutes or more to complete.

![](https://miro.medium.com/max/1400/1*KSE_-vmvf0AyA_S_N7e90Q.png)

#### Step 6: Confirm the receipt of your funds. Your crosschain transaction is complete!

Once your crosschain transaction is complete, you’ll see your $XRP balance on Wanchain (called $wanXRP), and the crosschain transaction status change to “**Success**”.

### Need help?

Join our [Telegram Tech Support](https://t.me/WanchainSupport) channel. Our support team is standing by and happy to help!

> **Note:** If you receive a DM offering help, block them immediately. Admins will never DM you first! Never share your seed words with anyone, period.
