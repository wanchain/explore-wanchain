# WanLend Operating Instructions

WanLend is a decentralized financial management platform, users can deposit cryptos to gain interests, or borrow cryptos and pay interests.

The deposit, borrow, interest rate generation and collection are all controlled by smart contracts. The borrowing function supports users to mortgage a defined crypto and borrow other cryptos from the contract.

## **1. Open the WanLend website**

Open WanLend with Google Chrome, URL: [https://wanlend.finance/](https://wanlend.finance/)

Connect to WanMask extension wallet;

The assets of your account will be displayed in your WanMask;

![](https://cdn-images-1.medium.com/max/2000/1*BoCqnRwNk7nkgIEFBZvpUA.png)

The WanLend page is shown as below:

![](https://cdn-images-1.medium.com/max/3100/0*_mBWSpI29rTpFaxM.png)

## **2. Deposit assets to gain interest rate**

Deposit your crypto assets which are supported on this page. Now supported assets for supply are: WAN, FNX, wanUSDC, wanBTC, wanETH, and wanUSDT, 6 types of assets.

After supplying, a ‘wToken’ will be generated and your interest rate will be calculated.

### **2.1 Authorization for the first supply**

Except WAN coins, the other 5 assets need to be authorized for the first time supplying.

Click a certain asset, the authorization window will pop up, click the Enable button, and confirm the authorization with WanMask;

![](https://cdn-images-1.medium.com/max/2000/1*wyQiFQX5NbS6SF3mxJgleA.png)

### **2.2 Supply**

In the supply area, click the token column you want to supply. In the supply window that pops up, enter the amount you want to deposit, then click the supply button, and confirm the deposit on the WanMask wallet.

Click the “Max” button to input the maximum amount with your balance;

![](https://cdn-images-1.medium.com/max/2000/1*d_i5xg7wdXOFyC90RgUuUg.png)

It should be noted that the deposit interest rate here refers to the annualized rate, and it is variable with each block.

### **2.3 Repay**

Assets with supply or loan will be displayed at the top of the column list first.

![](https://cdn-images-1.medium.com/max/2000/1*PfJPgXs1aoK-iwpMU9XxpA.png)

Click on the column and select the Repay tab in the pop-up window; enter the amount you want to withdraw, click the repay button, and confirm on the WanMask wallet;

![](https://cdn-images-1.medium.com/max/2000/1*CIGg1L8Wbn41GcTN6s0jxg.png)

Click the ‘MAX’ button to indicate that you want to withdraw all the amount within the safety threshold. **if you still have loans, pay attention to that in case the value of your collateralized assets depreciates, or the value of your borrowed assets rises, then the probability that the collateralized assets will be liquidated greatly increases.**

If you don’t have any loan at this time, it will withdraw all supplied assets with interest rates.

![](https://cdn-images-1.medium.com/max/2000/1*QW3-8tmE1vysl0KU6YzAxQ.png)

## **3. Collateralized Borrow**

After supplying the assets, the interests start to be calculated; but if you want to borrow, you need to collateralize the assets to get your borrow limit.

If you have collateralized a certain asset, you can no longer borrow this asset; similarly, if you borrow a certain asset, you are not allowed to supply this asset again; the relevant columns will be automatically hidden on the page.

### **3.1 Collateralization**

Click the Collateral switch on of the asset you want to collateralize, click the “Use as Collateral” button in the pop-up window, and confirm the authorization on the WanMask wallet.

You can also turn on the collateralization for assets without supplying first. In this case, once you supply such assets, it will automatically be added to your borrow limit.

![](https://cdn-images-1.medium.com/max/2000/1*2btBxpV5-XJ7-QGh2JfhkA.png)

![](https://cdn-images-1.medium.com/max/2000/1*buHnN-0u6MssTyKr2koicw.png)

### **3.2 Borrowing**

In the borrowing area, click on the asset you want to borrow. In the window that pops up, enter the amount you want to borrow, then click the Borrow button, and confirm the authorization on the WanMask wallet;

Click the “80% limit” button, it will display the maximum amount within the safety threshold that you can borrow at the current market price. The borrowing interest rate here refers to the annualized interest rate, and it is variable, and will change according to the amount supply-borrow ratio of the pool.

![](https://cdn-images-1.medium.com/max/2000/1*ZiH06e4I10a_fFeOEOFNXA.png)

### **3.3 Repayment**

In borrow markets, click on the asset you want to repay, and select the repayment tab in the pop-up window;

If it is the first repayment of the asset, authorization is also required;

Enter the amount you want to repay, then click the repay button, and confirm the authorization on the WanMask wallet;

Clicking the “Max” button to return all the borrowed amount and interest of the asset or the maximum balance of this asset in your wallet.

### **3.4 Liquidation**

In order to maintain the stable operation of the system and protect the safety of suppliers’ funds, WanLend has set up a complete set of risk avoiding and liquidation rules.

**If the value of your borrowed assets exceeds the loan limit, your account will be partially liquidated. This happens when the value of collateralized assets declines or the value of borrowed assets rises. Therefore, users shall pay attention to controlling risks and the price changes of related assets.**

The safe collateralized rate set by WanLend is 75%, which is the borrow limit (equivalent to an over-collateralization rate of 133%).

The maximum safety threshold is set to 80% of the loan limit.

Let’s take an example to illustrate. Assuming that 100 wanETH is collateralized when the price of wanETH is 1000$, your collateralized assets are equivalent to 100,000$.

Borrow limit = collateralized assets * 75% = 75,000$

The highest amount you can borrow = borrow limit * 80%=60,000$

a) If the borrowed asset is a stablecoin

For example, if you borrow 50,000 wanUSDT, assuming that the price of 1 wanUSDT is always 1$, you need to pay attention to the risk of wanETH price drop;

When the value of your collateralized assets, wanETH drops to 50,000 / 75% = 66,666.67$, wanETH will be liquidated;

That is, before the wanETH price drops to 66,666.67 / 100 = 666.7$, you must increase the collaterals or repay the borrowing wanUSDT to avoid liquidation.

b) If the borrowed asset is not a stablecoin

For example, if you borrow 50,000 WAN when the WAN price is 1$, you should pay attention to the risk of liquidation due to the price increase of WAN;

Assuming the current wanETH price is N,

When the value of your borrowed assets, WAN reaches (N* 100) * 75%, wanETH collaterals will be liquidated;

It is equivalent to the WAN price at this time (N* 100) * 75% / 50000 = 0.0015N

If the wanETH price is still 1000$ at this time, but the WAN price rises to 1.5$, liquidation will be triggered.

If the price of wanETH drops to 800$ at this time, then as long as the WAN price rises to 1.2$, liquidation will be triggered.

If the wanETH price rises to 1200$ at this time, then the WAN price will only rise to 1.8$ before liquidation will be triggered.

## 4. Supported assets by WanLend

* WAN

* wanBTC

* wanETH

* wanUSDT

* wanUSDC

* FNX

Other assets will be added in the future.
