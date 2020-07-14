
# Trezor Support

## Requirements
|**Hardware/Software**|**Version**|
|:---|:---| 
| [Wanchain GUI wallet](https://wanchain.org/products) | 1.0.5 or later  |
| [Gwan](https://github.com/wanchain/go-wanchain) |   1.0.5 or later|  
| Trezor One (Trezor T not supported) |   1.6.2 to 1.7.1|  

*You can find instructions for updating your Trezor firmware [here](https://wiki.trezor.io/index.php?title=User_manual:Updating_your_Trezor%27s_firmware&ModelType=1)*

## Step by Step Guide

*DISCLAIMER: MyWanWallet.nl is a Wanchain community project. The Wanchain Foundation does not maintain the project or make any guarantees about its security or functionality, and takes no responsibility for any loss or damages incurred through use of MyWanWallet.nl.*

1. Connect your Trezor to your PC by USB and navigate to [https://mywanwallet.nl/](https://mywanwallet.nl/). Double check the address to make sure that it is correct, including 'https' and the 'nl' domain.  

2. Double check that you are on the Wanchain Mainnet and not on the Testnet or any other network. 

3. Select "Trezor" from the radio menu

4. Click "Connect to Trezor" 

  ![](media/trezormww1.jpg)

5. Allow your browser to redirect you by popup to the url beginning with `https://connect.trezor.io`.

6. Wait for the page to load.

  ![](media/trezormww2.jpg)

7. Click the blue button with the text "Allow once for this session" to allow MyWanWallet.nl permission to read the public keys from your Trezor device.

  ![](media/trezormww3.jpg)

8. Click the green button with the text "Export" to export your Trezor device's public keys to MyWanWallet.

  ![](media/trezormww4.jpg)

9. Using the numbers displayed on your Trezor device together with the number pad displayed in your browser, input your Trezor device's passcode in order to export your public key.
  ![](media/trezormww5.jpg)
  
   ![](media/trezormww5a.jpg ':size=300')

10. Select the address with the WAN balance you would like to use, and then click the button with the text "Unlock your Wallet".
  ![](media/trezormww6.jpg)

11. You will now be redirected to your wallet details on MyWanWallet.
  ![](media/trezormww7.jpg)

12. Input the address you want to send to in the "To Address" field.

13. Input how many WAN you want to send in the "Amount to Send" field.

14. You may leave the "Gas Limit" at the default of 21000, and then click click the green "Generate Transaction" button to generate your transaction. 

  ![](media/trezormww8.jpg)

15. Allow your browser to redirect you by popup to the url beginning with `https://connect.trezor.io` and wait for the page to load.
  ![](media/trezormww9.jpg)

16. Click the blue button with the text "Allow once for this session" to allow MyWanWallet.nl permission to sign the transaction with your Trezor device.

  ![](media/trezormww10.jpg)

17. Confirm the transaction on your Trezor device by clicking the right button:

    ![](media/trezormww10a.jpg ':size=300')

18. Confirm again:

    ![](media/trezormww10b.jpg ':size=300')

19. You will be redirected back to the MyWanWallet page where you should click the green button with the text 'Send Transaction' to begin sending your transaction.

  ![](media/trezormww11.jpg)

20. Finally a pop-up window will display all of your transaction details. Please check all the details to make sure they are correct, and click the green button with the text "Yes, I am sure! Make transaction." to complete your transaction.

  ![](media/trezormww12.jpg)
