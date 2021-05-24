# WanWallet Offline

The Offline wallet can be used for extra security, and is also required for certain features such as the “partner-in” method of adding stake to POS and Storeman nodes.

## Features

The v3.0.0 version of the hardware wallet primarily features updates related to the newly added latest features such as the new Storeman node and wanBridge systems.

The wallet may be downloaded from the [Wanchain.org home page](https://www.wanchain.org/getstarted/).

The Offline wallet does not need to be connected to the Internet to generate valid signed transactions. The user simply fills in all the transaction parameters and then uses their private key to generate a signed transaction offline. The signed transaction may then be sent through a regular online wallet on another machine. The Wanchain desktop wallet supports the sending of transactions generated on the offline wallet.

## Main functions of WanWallet Offline

• Initiating staking, adding stake, adding “partner in” stake, and withdrawal from staking for Storeman nodes  
• Initiating staking, adding stake, adding “partner in” stake, and withdrawal from staking for POS nodes  
  
## Partner-in To Storeman

The “partner in” function allows multiple addresses to set up a node together. After the first person sets up their node with at least 10,000 WAN, anyone else may contribute stake to that node using the partner in function. Even though partnered in stake is contributed to another person’s node, it is still in control of the person who sent it. It is never in custody of the person who set up the main node address. The staking rewards, however, will all be sent to the main node address, and there is no on chain distribution of rewards. So please only partner in with friends you trust to fairly share the reward with you!

Partner in funds will earn rewards at the same rate as regular stake, which is higher than delegated stake.

For partner in, minimum amount that can be partnered in is 10,000 WAN, there is no maximum amount, and maximum of 5 addresses can partner in.

_Read on to learn how to partner in stake….._

### Prepare an Air Gapped Computer

Prepare a computer which has a clean install of your operating system of choice and which has never been connected to the internet or connected to any device with internet connection capabilities. Ensure that no cords are connected to your machine, and that all wireless connections are turned off, including bluetooth, wifi, or any other wireless communication methods.

Ensure that your computer is password protected and the contents are [encrypted](https://theintercept.com/2015/04/27/encrypting-laptop-like-mean/).

### Prepare the Offline Wallet

A) Download Offline Wallet on Another Computer

[Download the Wanchain offline wallet installer](https://www.wanchain.org/getstarted/) on another computer and copy it to a new and unused usb flash drive.

B) Install the Wallet

Transfer the wallet to your air gapped computer using the usb drive, and use the wallet installer to install it to your computer.

C) Create an Account

Click the Create button to create a new account.

Remember the account name and password.

![](https://miro.medium.com/max/875/0*yWjBMDS2OCGaMFBC.png)

After clicking “Submit”, a new account will be generated, in this example we have chosen the username of “L”.

### Back up the keystore file

Click the “Backup” button in the upper right corner, there you can see the directory where the keystore file is located.

In the file explorer, open the directory and back up the keystore file to your USB flash drive. After transferring the keystore to the flash drive, you should never re-connect the drive to a network connected device.

Save your USB drive in a safe place. We recommend you make several backup USB drives especially in case you are securing a large amount of assets as there is a small chance the drive may become corrupted.

### Transfer WAN to Your Address

The minimum amount of WAN required for “partner in” stake is 10,000. Don’t forget to also include some WAN for paying gas fees. 10 WAN should be plenty for gas.

### (DESKTOP WALLET) Get Your Transaction Nonce

Open the desktop light wallet on another internet-connected computer, and in the settings menu, select “Enable offline wallet”.

The offline wallet menu will appear, click “Offline Wallet” from the left menu.

![](https://miro.medium.com/max/875/0*Xa2x_I4NFLjaPQ8R.png)

In the first step, enter the address from the offline wallet which you are sending from using to send partner in funds (the one we have named “L”), and click the “Generate” button.

At this time, you can see the Nonce value.

![](https://miro.medium.com/max/875/0*J4zi7Z8MsAEG1KjC.png)

## (OFFLINE WALLET) Generate Signed Transaction

![](https://miro.medium.com/max/875/0*ElC_gB_wXibw7xNL.png)

1.  Click the “Sign” button to begin the signing process.
2.  Enter the Nonce you got in the previous step
3.  In the “To” field, Enter the Storeman smart contract address. [Check the official Wanchain Twitter account to confirm the address](https://twitter.com/wanchain_org/status/1327182410119835650).
4.  In the “Value” field, enter the number of WAN you wish to partner in with
5.  Click the “Customize” button, then click “Open Storeman”, then click “partIn”
6.  In the “wkAddr” field, enter the Work Address of the node you want to partner in to, then click the “Confirm” button.

Then change the value of Gas limit to 1000000. (At this time, the transfer fee should be 0.001 Wan)

![](https://miro.medium.com/max/875/0*k7ia5I55vfjjRhJP.png)

After confirming that the information is correct, click the “Sign” button, enter the account password and wait for the “Signed successfully!” prompt to appear.

![](https://miro.medium.com/max/875/0*QBjzyoXJHHE6L70W.png)

Copy the signed transaction data to a text file and transfer the file to an empty USB flash drive.

## (DESKTOP WALLET) Broadcast Signed Transaction

Connect your USB drive with the signed transaction to your computer with the desktop wallet open.

Copy the signed transaction and paste it into the empty field under “Step 3”

Click “Send Transaction”.

![](https://miro.medium.com/max/875/0*nP27kbk8OcfJZNeh.png)

After completing the transaction, you will be able to view it in your transaction history.
