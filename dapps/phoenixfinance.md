# Phoenix Finance — The decentralized derivatives marketplace.

![](https://www.phx.finance/static/logo-color.8fdff024.svg)

_All materials relating to Phoenix Finance were reproduced from [docs.phx.finance/](https://docs.phx.finance/) with permission on 2022/03/14._

## Introduction

**What is Phoenix?

Phoenix is the new open finance protocol currently live on Ethereum, Polygon, Binance Smart Chain and Wanchain. It is a DeFi platform specialised in crypto financial derivatives. Besides mining and staking opportunities, our users can trade both options and decentralized leveraged tokens.

Phoenix is pioneering a cross-chain DeFi protocol for writing options exposure for multiple assets from within collateral pools. This Multi-Asset Single Pool (MASP) methodology for decentralized peer-to-pool options platforms enables anyone anywhere to leverage or hedge their positions in a variety of cryptoassets.

The second product is the decentralized leveraged token protocol, launched on Polygon, Binance Smart Chain and Wanchain in Q3 2021. It provides a decentralized way for creating and trading decentralized leveraged tokens on cryptoassets, like BTC, ETH, etc., on different chains. It alse provide stable leverage, simplicity and do away with the usual difficulties associated with trading on margin.

**PHX Token**

The PHX token is the network token for the entire suite of Phoenix protocol clusters. It serves a variety of purposes including liquidity mining, governance, voting, reward boosting and more.

## Products

### Options (PPO)

**Introduction**

PPO stands for Phoenix Protocol for Options. It is one of the main products of Phoenix Finance.

PPO provides a decentralized way for writing and trading options. All the core functions of options - writing, trading, exercising, settlement, etc., occur on-chain and are managed by smart contracts. It is a permissionless, censorship-resistant, and non-custodial protocol. PPO’s goal is to make it simple to buy and exercise options in an easy, secure and decentralized way.

- It creates a friendly transaction venue for option sellers to provide liquidity in the pool and earn passive rewards. The options collateral pool is working as the collective sellers of options and premiums are automatically distributed. Risks are also diversified by varieties of live options.
- In addition to providing an attractive return for option writers, this model is also friendly to options buyers. They will be able to benefit from the wide variety of option types supplied by the pools and able to tailor strategies suitable to their needs. Buyers can also combine customized option terms in a variety of ways, enabling the creation of complex and powerful strategies. The model is easily extensible and is only limited by the amount of capital included in its collateral pools.

In a nutshell, PPO v1.0’s elegant mechanisms serve to benefit both liquidity pool contributors (liquidity providers or LPs) and options buyers/traders. No other DeFi options protocol currently sports our Multi-Asset Single-Pool (MASP) model, which we believe is the best way to bring together a fractured liquidity landscape for on-chain derivatives and thereby ensure the best possible trading experience for our LPs and other users.

PPO v1.0 has been audited by PeckShield.

**Options Basics**

_What is an option?_

An option is a binding contract that allows you (as the buyer) to sell or buy an underlying asset (goods, stocks, indexes, etc.) at a predetermined price within a set time frame. You as the buyer of an option contract, have the right, but not the obligation, to buy or sell the underlying asset. That’s the big difference between options contracts and futures contracts. With futures you are obligated to take delivery of the underlying asset. In the case of oil, since there are some costs associated with delivery and storage of the underlying, futures contracts can actually be negatively priced!

With options, in order to get that right to buy or sell a particular asset at a predetermined price, you have to pay the option seller a price, which is called the **option premium**.

For example, a fruit store wants to buy 500 kg of apples from an orchard owner, but the apples are not ripe yet until August. The fruit store worries about the rise of the price, affected by drought this year. Therefore, it reaches an agreement with the orchard owner, that it may purchase the apples at the price of $4/kg in August. But it doesn’t have to do so if there is some cheaper price on the market. In order to have this right, the fruit store pays the orchard owner $100 as compensation.

The contract above is a typical option. It is called a [Plain Vanilla](https://www.investopedia.com/terms/p/plainvanilla.asp) call option.

The following terms are essential to understanding the nature of options products.

_Option Buyers and Sellers_

Each option contract has two parties, the option buyer/holder and the option seller/writer. Unlike a futures contract, with options, the rights and obligations of the two sides of this equation (called “counterparties”) are not parallel. The option buyer pays the option premium and is entitled to rights only. The option seller receives the premium as consideration for giving up those rights.

_Collateral Requirements_

Due to the counterparty relationship described above, the buyer/holder of an option may just sit there and see how the market goes, waiting to decide whether to exercise the right or not. On the other hand, the seller/writer of an option has an obligation. Whenever the holder decides to exercise his option, he/she must settle according to the terms of the option contract. Therefore, a security deposit or collateral of some sort, must be handled to ensure the contract will perform accordingly.

_Risks_

The buyer and seller of an option contract will be exposed to very different levels of risk.

In buying options, the risk is limited to the premium paid for the option — no matter how much the actual underlying asset price moves adversely in relation to the strike price. For example, in the apple example from my previous post, the fruit store, as the option buyer/owner, has a maximum potential loss of $100. If the price of apples actually drops in August, it may just choose not to exercise the option contract.

In selling options, the risk can theoretically be unlimited, if the option seller/writer chooses not to hedge his position in some other transaction. When selling a call option, if the price rises above the strike price, it is in the best interest of the option holder to exercise the right to purchase the underlying asset at the previously agreed upon strike price, since it would be cheaper than the current market price. Because the option writer is locked into this strike price due to the obligation that was incurred when accepting the option premium, the option seller is subjected to losses, with theoretically no potential limits. For example, in our apple example, if some drought happens and the market price of apples doubles or triples, but the orchard owner is contracted to sell at $4/kg, they will have big losses compared to what they could have received if they had not sold the option. The higher the market price is, the more the orchard owner will suffer.

_Potential Returns_

Due to the unparalleled nature of the rights and responsibilities of the buyer and seller, their returns are also distributed quite differently. An option seller (which is effectively a short position on the derivative contract) can only profit from the receipt of the option premium, yet may suffer from losses if the market price moves in unfavorable directions.

1) The profit-loss chart of shorting (selling) and longing (buying) a call option looks like this:

![](https://miro.medium.com/max/1250/1*NqLVFFfwxa7TUOkgAWlUjg.png)

A call is a bullish position on the underlying asset.

When shorting a call, one is at profit in the green zone, when the price is not higher than the Break-even point. The maximum profit for the option writer/seller is the amount of the premium when the price is not higher than the strike price and therefore the option would not be exercised, expiring worthless. When the option seller/writer is at a loss in the red zone, there is no limit to the losses as the market price rises.

When longing a call, the option contract will not be ‘activated’ if the market price is lower than the strike price. Hence, the option buyer/holder is paying a premium for nothing. However, when the price moves above the strike price, the option buyer/holder will exercise the contract; but he/she will still be at a loss on the investment until the price of the option reaches the Break-even point, which is the amount of the option premium. As the price of the option moves above this threshold, the profit for the option buyer/holder increases, with theoretically no limit. The only bound is the time to expiry of the option.

2) The profit-loss chart of shorting (selling) and longing (buying) a put option looks like this:

![](https://miro.medium.com/max/1250/1*FZLhy9a_6R2R5ujeZ8DhIw.png)

Remember that a put is a bearish position on the underlying asset. It is a right to sell the underlying asset at a particular strike price. It is the opposite of a call option.

When shorting (selling) a put (which is a bullish position on the underlying asset), one is at profit in the green zone, when the price is not below the Break-even point. The maximum profit for the option seller/writer is the premium paid for that option when it was created. The goal for the option seller/writer is that the price of the underlying asset remains higher than the strike price obligated in the option contract, meaning that the put option would not be exercised. The option seller/writer is at a loss in the red zone. The loss will be more significant as the market price decreases.

When longing (buying) a put (which is a bearish position on the underlying asset), the option contract will not be ‘activated’ if the market price is higher than the strike price; hence the buyer is paying a premium for nothing. However, if they also hold the underlying asset, they still will enjoy the gains from the price appreciation there. In this scenario, the put option functions as **insurance** for the holder of the underlying asset.

The put option itself is in profit for the option buyer/holder when the price of the underlying asset moves under the strike price. Then, the holder will exercise the contract. However, the option buyer/holder remains at a loss on the investment until the the price rises above the break-even point, which is the price that was paid for the option premium. The profit of the option buyer/holder increases as the price of the underlying asset moves even lower.

_How options are priced_

There are several popular options pricing models, like the [Black Scholes Model](https://www.investopedia.com/terms/b/blackscholes.asp) and [Binomial Option Pricing Model](https://www.investopedia.com/terms/b/binomialoptionpricing.asp#what-is-the-binomial-option-pricing-model). I am not going to delve into the mathematical details of these models, yet it is useful for option investors to learn the basic interrelations among the different factors affecting the price.

![](https://miro.medium.com/max/3000/1*lmqbfCBFyK3lLJdkIxxMjg.png)

1) If the market price of the underlying asset increases, the buyer/holder of a call option will be more likely to exercise the call option. They would receive more benefits by exercising the call option and owning the underlying asset. Hence, in this bullish scenario, the right conferred by the call option brings more positive economic benefits to the option buyer/holder and the call option will have more value. The option buyer/holder can also choose to sell the option itself rather than exercising the option. They still benefit from the increase in economic value. In the case of put options, the case will be the opposite. In short, the market price of the underlying asset will have a positive correlation with the call option price, while it has a negative correlation with the put option price.
2) If a call option has a lower strike price, it means that the holder will have a right to buy the underlying asset at a cheaper price. Thus, the right contained in the option will be more likely to bring economic benefits to the option buyer/holder. As a result, the call option will be priced higher on the market. While for a put option, the case will be the opposite. In short, the higher the strike price of an option contract has a negative correlation with the price of a call option, while it has a positive correlation with the put option price.
3) The longer the time to expiration of an option, the more uncertainty an option writer/seller is exposed to. Thus, the right given to option holders/buyers has a higher value. The same logic applies to both call and put options. With more time, there is more chances to have explosive movements in price, especially in the cryptocurrency markets. Therefore, option price is positively correlated with the time to expiration.
4) The higher the price volatility of the underlying asset, the less predictable is the future price of that asset. Thus, the right conferred to option holders/buyers has more value. From the same perspective, the risk undertaken by the option writer/seller is much higher, which gives them the ability to charge more for the option premium. Therefore, the option price is positively correlated with volatility.

**Options Strategies**

_Holding a call to speculate_

The long call option strategy is the most basic option trading strategy, whereby a user buys call options with the belief that the price of the underlying asset will rise significantly beyond the strike price before the option expiration date.

![](https://aws1.discourse-cdn.com/standard17/uploads/community12/original/1X/0bce6bc743ed0c8d30a496a7ad594c2199ebec5f.jpeg)

Sam is a ETH hodler and he is bullish due to the growing DeFi ecosystem on Ethereum. He is holding 1 ETH already. To maximize his gains if the ETH price goes up in the near future, Sam buys 1 ETH call with the strike price of $700 and the expiry of 15 days. The premium is $70 for each contract. If the price grows by 20% to $840 in two weeks, Sam will get $140 ( 840-700 ) by exercising the call, and the return is 100% ( ( 140-70 ) / $70 ). The call gives Sam a 5x leverage in return.

If the price drops by 20% to $560 in two weeks, Sam will not exercise the call option and $70 is all he can lose. But for holding one ETH, Sam may lose $140 from the collapse.

If Sam is extremely bullish and he can even deposit ETH on Makerdao, Compound or Aave, to borrow stable coins to buy call options. This will give him even further leverages, and higher risks.

_Protective Puts: A Hedging Strategy_

A **protective put** position is created by buying (or owning) an asset and buying put options with a strike price equal or close to the current price of the asset.

A protective put strategy is analogous to the nature of insurance. The main goal of a protective put is to limit potential losses that may result from an unexpected price drop of the underlying asset.

Adopting such a strategy does not put an absolute limit on the potential profits of the investor. Profits from the strategy are determined by the growth potential of the underlying asset. However, a portion of the profits is reduced by the premium paid for the put.

![](https://aws1.discourse-cdn.com/standard17/uploads/community12/original/1X/2958cb8fb0e32b2ffb508249f3456f3faa1652b7.jpeg)

Example of Protective Put: You own 100 ETH, with each ETH valued at $500. You believe that the price of ETH will increase in the future. However, you want to hedge against the risk of an unexpected price decline. Therefore, you decide to purchase 100 protective put contracts with a strike price of $500. The premium of one protective put is $10.

_A Covered Call to Benefit From a Flat Market_

A covered call is created by owning an asset and selling an equivalent amount of call options. To execute this strategy, a trader holds a long position in an asset and writes (sells) call options on that same asset to generate an income stream.

![](https://aws1.discourse-cdn.com/standard17/uploads/community12/optimized/1X/9e53e3ba617863002bb971e12f725c8658ddb441_2_1035x655.jpeg)

Lucy is holding ETH with a price of $750. She expects that the market will stay flat for a while and wants to possibly lower her cost in the flat market. Therefore, she decides to sell ETH calls with the strike price of $760 and earn the premiums of $50 immediately. If the price gets higher than $760, she will sell when the option buyers exercise the calls. If the price stays lower than $760 till expiration, she will still get premiums and lower the cost of holding one ETH by $50.

In this example, Lucy employs a covered call strategy as she intends to hold the underlying asset for a long time but does not expect an appreciation in price in the short term, and she is satisfied with selling the assets at a predetermined price.

Please note that PPO v1.0 on Phoenix Finance doesn’t allow for selling options for now.

_Straddle Strategy_

A straddle is a strategy accomplished by holding an equal number of puts and calls with the same strike price and expiration dates.

A straddle is meant to take advantage of the market price change by exploiting increased volatility, regardless of which direction the market’s price moves. For example, I am not sure BTC is going to go upwards or downwards in the coming days. But I expect the movement will be big. I can buy a straddle from FinNexus options platform.

Suppose I buy a call and a put together with the strike price $19000. If the market moves up, the call is there; if the market moves down, the put is there. It may cost me like 500 USD in total. If the BTC rises above 19500, or fall below 18500, I will end up in profit. What is more beneficial is that I can exercise the options and collect the profit anytime before they go expired.

This is a typical straddle strategy.

_Strangle Strategy_

The **long strangle** involves going long (buying) both a [call option](https://en.wikipedia.org/wiki/Call_option) and a [put option](https://en.wikipedia.org/wiki/Put_option) of the same underlying security. Like a [straddle](https://en.wikipedia.org/wiki/Straddle), the options expire at the same time, but unlike a straddle, the options have different [strike prices](https://en.wikipedia.org/wiki/Strike_price).

![](https://aws1.discourse-cdn.com/standard17/uploads/community12/original/1X/e6c44ffaa78cc4012afff1b0e1ebb327f51be4f6.png)

A strangle is a good strategy if you think the underlying security will experience a large price movement in the near future but are unsure of the direction. However, it is profitable mainly if the asset does swing sharply in price.

The cost of a strangle can be lower than a straddle, as the options are [OTM](https://www.investopedia.com/terms/o/outofthemoney.asp). The example is just like the one in the straddle strategy, well with different strike prices.

_IL Hedging_

[Hedging Against Impermanent Loss](https://coinmarketcap.com/alexandria/article/hedging-against-impermanent-loss-a-deep-dive-with-finnexus-options) on Coinmarketcap Alexandria by Phoenix Finance Cofounder Ryan Tian

**PPO v1.0 MASP – Multi Asset Single Pool**

_The Universal Options Protocol_

PPO v1.0 is a universal options protocol that enables the creation and trading of options or other derivatives from any type of underlying asset based on the collateral held in liquidity pools. Our mechanism is universal, in the sense that it provides both universal support for any underlying assets, as well as universal support for a variety of innovative models for options issuance.

PPO v1.0’s pooled liquidity enables users to buy options directly through the protocol smart contract without individual counterparties. In the current construction of PPO v1.0, a separate liquidity pool must be maintained on each respective chain.

There is no limit to the types of options that can be created with the protocol. Any asset can be an underlier for PPO options — including cryptocurrencies from any blockchain, fiat currencies, commodities, equities, and practically any asset with a reliable on-chain price feed. Under this version of our protocol, it is not necessary for assets to exist in a tokenized form on-chain. The options are synthetically derived from an oraclized price feed itself.

![](https://z3.ax1x.com/2021/07/20/WNUsEt.jpg)

The basic call/put options introduced with v1.0 serve as a foundation for many other combinations of options strategies (straddles, strangles, etc.). PPO users will be able to create their own unique portfolio tailored to their individual risk/return requirements. As we expand the number of assets included, these tools will become increasingly useful in creating bespoke strategies.

_How Does the Liquidity Pool Work in PPO v1.0?_

The unique MASP system — Multi-Asset Single-Pool — allows the users to gain exposure to a variety of bespoke cash-settled options positions on a variety of underlying assets, like BTC and ETH. More underlying assets are likely to be added in the future.

The following graphic describes the different roles in the pooled system — Options Buyers and Pool Participants (LPs) — as well as the different actions — selling, exercising, and contributing or withdrawing collateral assets.

![](https://z3.ax1x.com/2021/07/20/WNUDHI.jpg)

_Pooled Options Model Basics_

1) PPO v1.0 will be live on multiple chains with the same mechanisms.
2) Collective liquidity/collateral pools are created with collateral assets. The pools then act as the seller of all the options. The protocol may accept other crypto assets as collateral for the pool in later versions and/or on different blockchains.
3) Options will not be tokenized. Rather they will be recorded in smart contracts.
4) The initial underlying assets are BTC and ETH, but can be extended to any assets. The long-term vision includes the creation of bespoke options positions on any cryptocurrency, stock, physical assets, index or really any asset with a dynamic price feed.
5) Options will be American type and can be exercised any time freely before expiration against the single liquidity pool on the chain where the exposure is held. Some restrictions may be understandably added in the first few iterations here to control risks. For example, a one-hour chill time restriction is added.
6) Pool shares are tokenized as PPT tokens and sent to pool participants as certificates.
7) The pool size is measure by the net value in USD, which changes according to the distribution of premiums, moneyness of options, exercising, sell-back, and other associated features.
8) The buyers can choose option characteristics according to their needs. The associated premium will be calculated using algorithms in the smart contracts, dynamically and automatically.
9) Protocol security will be maintained by setting the collateral level high to guard against black swan events. The collateralization ratios for stablecoins are set to be 120%.
10) Collateral assets in the pool can be withdrawn anytime, provided the liquidity is not fully locked by the existing option contracts. Again, some restrictions may be added in the first version. For example, a one-hour chill time restriction is added.

_PPO v1.0 MASP Pool Overview_

MASP stands for Multi-Asset-Single-Pool. It is the core mechanism applied in Phoenix’ decentralized peer-to-pool options protocol, with liquidity pools as the counterparty for writing and settling option contracts.

'Multi-Asset' features in the liquidity pools enable the creation and trading of options from any type of underlying asset, including crypto assets, commodities, fiats, stocks, indexes, and more. The potential for underliers is unlimited.

'Multi-Asset' also means that there can be multiple types of crypto assets in the liquidity pool. For instance, PPO v1.0 has a hybrid stablecoin pool including USDC, USDT as the currencies for settlement. It may develop with more assets by this 'Multi-Asset' feature.

'Single-Pool' does not mean that there is only one pool in PPO v1.0. While one liquidity pool may power many different options contracts. Liquidity can be shared automatically, different from the traditional order books.

Notice also that the MASP (Multi-Asset Single Pool) pools in the PPO are very different from liquidity pools on other DeFi platforms like Uniswap, Curve or Balancer. These two, in particular, behave as automated market makers for cryptocurrency swaps. MASP Liquidity powered by collateral tokens is a liquidity solution for both the creation and settlement of options contracts, acting as the collective options seller.

The unique MASP system allows the users to gain exposure to a variety of bespoke cash-settled options positions on a variety of underlying assets.

_Pools as Collateral_

One typical requirement of options contracts is that the seller has the obligation to perform if exercise of the option is triggered by the holder. Thus, when writing options, there must be enough collateral (margin) locked up within the smart contract to ensure that it will be settled accordingly. The MASP liquidity pools operate as collective collateral.

_Pools as Trading Counterparty_

Some DeFi options projects have experimented with different liquidity solutions for options, like order books or the DeFi-inspired method of using Uniswap AMM pools.

However, both mechanisms face issues. In the former case, traditional order books are inefficient and it can be expensive to maintain a sufficient liquidity depth while also adhering to decentralization principles. In the latter case, it is likely that the pool participants will suffer from impermanent loss due to the inherent time decay of the value of options.

The Phoenix MASP liquidity solution provides a cost-effective and capital-efficient solution for trading DeFi options in a decentralized manner. The collective pools serve as the trading counterparties for options transactions and settlements.

_Pools Administered by Smart Contracts_

Options exposure sold to options buyers will earn options premiums. These premiums will automatically accrue in the liquidity pools and, as premiums compound over time, they are administered by smart contracts.

Since this pool is the counterparty for all live options, including all puts and calls with various underlying assets at different strike prices and expirations, the risk from any single option contract is diluted by the depth of the pool.

In addition, DeFi’s open-source nature ensures that the operations in the pools are censorship-resistant and publicly on-chain. In this regard, they are completely different from the black boxes some pools turn out to be in traditional finance.

The MASP automatic mechanism provides greater efficiency and encourages users to participate in trading as options writers.

_The Net Value of the Liquidity Pool_

Contributors that deposit their tokens in pools will receive PPT tokens that track a pro-rata share of their ownership in the options liquidity pools. As such, it is important to understand how the value of those tokens is calculated.

_What Is Pool Net Value?_

The Pool Net Value measures the monetary value of all the options exposures currently in the liquidity pool. It is calculated on the basis of accrual accounting and, as a result, may not be equal to the sum of actual net inflows and outflows at a given time.

Potential gains and losses to the liquidity pool, as the counterparty to the collective value of all options exposure sold from the pool, are reflected in changes to the Pool Net Value. In PPO, Pool Net Value is an important concept in deciding the pool size, which in turn determines the maximum value of options that can be written on the market, and, at the same time, measures the value of potential user claims from the pool.

_What Affects Pool Net Value?_

Let us take the USDC pool for example. (The other liquidity pools follow the same principles as described below.)

The total Pool Net Value (PNV) in USD is affected by the following factors:

1) USDC deposits increase the PNV;
2) USDC withdrawals decrease the PNV;
3) Receiving option premiums increases the PNV, with the caveat that the premiums accrue to the PNV over time as the options within the pool move towards maturity. This accrual mechanism is explained in more detail below;
4) The change in the intrinsic value of options (otherwise known as the “moneyness” level) increases or decreases the PNV. If an option goes further in the money, the intrinsic value is higher and benefits option holders. Hence, the PNV would decrease. If the option goes further out of the money, the intrinsic value of the options exposure printed by the pool would be lower and thus the PNV would be higher because the pool, acting as counterparty, would have reduced obligations;
5) Exercising options leads to a cash settlement that decreases PNV;
6) Selling options to the pool allows options holders to receive consideration from the pool and leads to the termination of the options contract, which in turn decreases PNV; (Currently disabled in v1.0)
7) The change in USD value of the USDC token increases or decreases PNV.

_Calculating Pool Net Value_

With the principles above, we can put the Pool Net Value (PNV) at the time of T as NetValue_T into the following formula:

![](https://cdn-images-1.medium.com/max/2030/1*PCvtVgynlWfc2pXiibPcOA.png)

Where,

1) p(T) is the USD price of USDC at the time of T.
2) N(T-1) is the number of USDC in the pool at the time of T-1.
3) Input(T) is the number of USDC tokens that are input into the pool during the time between T-1 and T.
4) Output(T) is the number of USDC tokens that are withdrawn out of the pool during the time between T-1 and T.
5) Premium(T) is the USD amount of premium that should be distributed into the pool, during the time between T-1 and T. Please check the details of calculation in the ‘Options Premium Distribution’ section below.
6) △IntrinsicValue(T) is the change of the intrinsic value of the existing options and the options that get exercised during the time between T-1 and T.
7) Sellback(T) is the USD value of the options that are sold back to the pool by the option holders during the time between T-1 and T. (Currently disabled in v1.0)

_Options Premium Distribution_

As mentioned above, Premium(T) is the measurement of premium distribution during the time between T-1 and T. In particular, we need to highlight the unique method utilized in the PPO to distribute options premiums to liquidity providers over time.

As consideration for the right given to option holders, premiums are paid into the pool all at once, at the time of purchase. However, due to the nature of all options contracts, that they are valid within a certain period of time until expiry, and based upon the accrual method of accounting, the options pool itself should not book the premium income all at once, either at the time of purchase or expiration. The premium, therefore, must be distributed into the pool in line with the level of seller obligations as time moves closer to expiry, or as the ratio of the time value of options decays with time.

Therefore, at time T, the premium of an option distributed into the pool is calculated as

![](https://cdn-images-1.medium.com/max/2000/1*F5N1ojg6ln6STG-4V-Okfg.png)

Where E(i) is the expiration of the option ‘i’, and Premium(i, Ei-T) refers to the premium of an option, calculated by [the Black-Scholes model](https://www.investopedia.com/terms/b/blackscholes.asp), with exactly the same terms and parameters as the option ‘i’, but with a different expiration of E(i)-T.

The difference in the above formula is the time decay of the value of the option ‘i’ as the time moves from T-1 to T, which should be accrued into the pool. When T=E(i), it means the time moves to the expiration time, and the premium in the last time slot will be fully distributed, where

![](https://cdn-images-1.medium.com/max/2000/1*GR2dKLEGaQ1WyfyRt4weGw.png)

Premium(i,0) means the option i goes to expiration, and it is the same as the intrinsic value.

What if the options are sold back to the pool or exercised during the time period T-1 to T?

Then the options will cease to exist after the time T, and the obligations of the option sellers will be gone. Hence the seller, which in this case is the monolithic liquidity pool itself, will be fully entitled to the premium not distributed before. Afterward, the rest of the unaccrued premiums will be allocated all at once. At time T, the premium of an option ‘e’, that is sold back or exercised, distributed into the pool is calculated as:

![](https://cdn-images-1.medium.com/max/2000/1*fVeAfUpXFwQe7Tr3akSgQQ.png)

Note that the selling-back function currently disabled in PPO v1.0.

Therefore, the Premium (T), the USD amount of premium that should be distributed into the pool, during the time between T-1 and T, can be calculated as:

![](https://cdn-images-1.medium.com/max/2000/1*A1szBvmg89efk2cPawaNtw.png)

Where N is the number of the equivalent options.

_The Net Value of the Pool Share Token (PPT)_

Following the previous USDC pool example, after a user puts USDC tokens into the pool, the USDC will be collateralized, and the holders will be entitled to the benefits of having a fraction of the liquidity pool. A pool share token will be minted and delivered to the users, to represent the pro-rata share in the USDC options pool.

The pool share token is called PPT, which stands for Phoenix Pool Share Token. PPT is transferable.

The net value of PPT is calculated using the Pool Net Value (defined above) and dividing by the total number of PPT tokens.

![](https://cdn-images-1.medium.com/max/2000/1*NYakDnLLOJVa9hPEkSe7Zg.png)

_Liquidity Pool Operations_

_Entering the Liquidity Pool_

Any users holding collateral assets can participate in the liquidity pool, getting option premiums and other returns, by depositing collateral assets into the pooling smart contract. A simple UI is designed for users to make inputs and interact with the smart contract. PPT tokens will be minted and delivered as pool share certificates.

The number of PPT tokens one may get is determined by the value of asset input into the pool in USD, and the net value of PPT at the time of depositing:

No.of PPT=(Assets input in USD)/(Net Value of PPT)

For example, if the Net Value of PPT is 1.5 USD, by depositing $150 worth of USDC, one may get 100 PPT in return.

_Exiting the Liquidity Pool_

Pool participants may exit the Liquidity Pools at any time, provided the collateral in the pool is not fully utilized and the collateral utilization ratio is over the Minimum Collateralization Ratio (MCR).

In cases when the collateral utilization ratio is below the Minimum Collateralization Ratio (MCR), pool withdrawal will be paused. The liquidity pool will also cease to write new option contracts until the collateral utilization ratio recovers to be above the MCR level.

By simply pressing the withdraw button, pool participants may withdraw the collateralized crypto assets partly or in full out of the pool. This operation will burn the related PPT tokens and the equivalent amount of crypto assets in the pool will be delivered at the net value of PPT at the time of withdrawal. Notice that in hybrid pools, the withdrawal is done proportionate to the composition of assets in the pools.

After withdrawal, the pool net value and the collateral utilization ratio will change accordingly.

_Liquidity Pool Security (Collateralization)_

In traditional finance, the performance of an options contract is ensured by the centralized third-party custody solutions that regularly compel and enforce the maintenance of sufficient collateral deposited from the options seller.

On a DeFi options platform, with the help of decentralized smart contracts, the seller/writer of options can deposit and collateralize a certain amount of margin - the collateral - in the smart contract to automatically ensure the exercise and performance of the option contract.

In the MASP options model of PPO v1.0, the liquidity pool acts as the only collective counterparty for all options. Pool participants each own a fraction of the total liquidity. Therefore, maintaining the security of the liquidity pool as a whole is crucial to making sure that the issued options are always fully backed. In other words, the collateralization ratio of the pool should be high enough to safeguard against massive market movements and other black swan events.

> The minimum collateral ratio of stablecoins in the liquidity pools is set at 120% .

However, in accordance with the essence of DeFi’s experimental nature, this threshold may be raised or lowered in the future in accordance with user response and the robustness of the protocol.

Collateral Ratio=(total collateral value)/(the collateral utilized amount)

The collateral ratio is calculated as the ratio of the total collateral value over the amount of collateral used to back options exposure written. The utilized amount is the total USD value of the strike assets in the live options. For one put option, the utilized amount is the strike price in USD. For one call option, the utilized amount is the current price of the underlying asset in USD.

![](https://cdn-images-1.medium.com/max/2000/1*pzBXiWNQUB2i79Qj9PfCXQ.png)

where N(c) is the number of call options; N(p) is the number of put options; SP is the strike price; P(underlying) is the current price of the underlying asset.

_Options Pricing_

Options in PPO v1.0 are priced according to the [Black-Scholes Option Pricing Model](https://www.investopedia.com/terms/b/blackscholes.asp). The pricing mechanism is coded in the smart contracts.

The value of a call option is:

![](https://cdn-images-1.medium.com/max/2000/1*-qEklRC_9iaua9CGUwOC-w.png)

The price of a put option based on [put-call parity](https://en.wikipedia.org/wiki/Put%E2%80%93call_parity) is:

![](https://cdn-images-1.medium.com/max/2000/1*QUc1bIBOVPHjEPbP8VkInA.png)

For both, as above:

N(·) is the cumulative distribution function of the standard normal distribution;

T-t is the time to maturity;

S is the spot price of the underlying asset;

K is the strike price;

r is the [risk-free rate](https://en.wikipedia.org/wiki/Risk_free_rate);

σ is the [volatility](https://en.wikipedia.org/wiki/Volatility_(finance)) of returns of the underlying asset.

When buying and selling options on PPO v1.0, the options are priced according to the Black-Scholes formula implanted in the smart contracts. Key parameters for pricing options include asset price feeds and Implied Volatility (IV).

In order to make the pricing mechanism more dynamic, an additional adjustment coefficient is added to the pricing formula to make the pool more balanced with regard to risk. The adjustment coefficient is subject to change according to the puts/calls ratio on the market and the overall utilization of the pool. The coefficient will behave in a manner that dynamically makes the calls/puts more expensive, if there are more calls/puts issued and backed by the collateral pool.

_The Options Market_

_Buying Options_

By purchasing call options, you are taking advantage of leverage, allowing you to use less money to gain positive exposure to the price of the underlying assets.

By purchasing put options, you are buying protection or insurance, to protect yourself against potential price drops of the underlying asset. Essentially, you are betting against an increase in the token price.

The trading venue is created automatically with the pooled liquidity.

When buying options, the pool collectively acts as the seller/writer; when a holder exercises options, the pool is the settler. There is no need to wait for orders to be filled, as is the case with traditional order books. The liquidity for all options is concentrated in the related liquidity pool.

This mechanism solves the liquidity and slippage issues experienced by most centralized exchanges.

_Customizable Options_

A clear benefit to options buyers in PPO v1.0 is that they can choose the terms of the options at their own discretion. They can create their own bespoke option by choosing option type, strike price, or expiration date. Option buyers can buy in-the-money (ITM), out-the-money (OTM), or at-the-money (ATM) calls and puts, with shared liquidity.

One can choose an options strategy that best suits one’s own unique individual risk profile, and may further combine it with different options or other derivatives, to create complex investment portfolios.

_Exercise an option_

Options in PPO v1.0 are all American types. Once a buyer purchases an option and becomes the holder, he/she may exercise the options, partly or fully, any time before expiration, but only after chill-time has passed since the purchase.

Notice that in hybrid pools, the assets on may get by exercising options are settled proportionate to the composition of assets in the pools. For example, in USDC/USDT hybrid pools, one may get a combination of USDC/USDT coins by exercising an option contract.

_When Can I Exercise?_

Options in PPO v1.0 are all American type options and, as such, can be exercised anytime before expiration.

_Should I Exercise?_

It is entirely up to the holder of the options whether or not and when to exercise an option. Whether it is financially beneficial for the option holders to exercise comes down to personal choices. The system of oracles and smart contracts that comprise PPO v1.0 will not make this decision on behalf of options holders.

_What Happens When I Exercise My PPO Option?_

Phoenix options will be cash-settled, denominated in PHX tokens, which means that only the difference in price will be settled. The difference between the strike price and the market value of the underlying asset will be exchanged into the collateral assets via smart contracts and transferred into the option holder’s address.

When exercising, if a call option is in the money, the option token holder will get the following amount from the liquidity pool:

![](https://cdn-images-1.medium.com/max/2000/1*0CReBebmiEWJZftKg8O1vg.png)

If a put option is in the money, the option token holder will get the following amount from the liquidity pool when exercising:

![](https://cdn-images-1.medium.com/max/2000/1*TzpFTqkwE3vknQcjDLhPLg.png)

The same logic applies to other liquidity pools.

When more than one type of crypto assets are collateralized in the pool, a combination of these assets, proportionate to the composition of the liquidity pool, will be settled and delivered to the holder’s address.

_Fees_

PPO v1.0 currently charges 5% of the total premium as transaction fee from the option buyers, and 5% of the cash settlement as settlement fee from the option holders when exercising options.

_Oracles and Price_

All values of the crypto assets, including both the collateral assets and underlying assets, will be calculated and measured in US dollars.

Phoenix Finance has integrated Chainlink’s Price Feeds to power our PPO platform.

**PPO v1.0 MASP – Multi Asset Single Pool**

_Priced with probabilities_

Measuring the financial performance in the collateral pool is not as straight-forward as for the other liquidity pools. Options are playing with odds, and the well-known BS options pricing model is based on the theory of probabilities. ‍ Based on the mathematical statistics, the writers are more likely to win in general if the options are properly priced, but in real application scenarios, things could be more complicated. The pool is the writer of all options with different terms: it is a mutual fund for writing options. It could take months or even years to prove the reliability and stability of the returns in the options collateral pool — but there are still ways to run some tests on what the financial picture will look like in the pool.

It is widely accepted that cryptoassets like Bitcoin (BTC) and Ethereum (ETH) are extremely volatile. Therefore, it would be reasonable to comprehend that options could be more friendly and beneficial to the holders rather than the sellers, as they only have rights without obligations, and the cost is capped to the premium.

_How to measure the Financial Performance in the Pools_

Before we jump into the mathematics, it is important to understand that volatility is an important parameter for pricing options. Options will be more expensive in more volatile assets. It is often known as implied volatility in pricing options in the BS model. Here in the following analysis, we use the historical average volatility to price options.

First, for BTC options, we calculate the historical average volatility in 2.5 years between Mar. 29, 2017 and Nov. 26, 2019, including a volatility of 1 day, 2 days, 3 days, 7 days, 15 days and 30 days.

Second, we calculate the price of ATM options with each expiration date with the volatility above, in the past 12 months, from Nov. 27, 2019 to Nov. 27, 2020.

Third, suppose the same amount of puts and calls is written by the pool, we can derive the P&L for the sellers in each expiry in the same period.

Last, we allocate different weights to the options in different expiry, referring to the transaction volume on Deribit. We can derive the pool’s average expected APR and the [maximum drawdown](https://www.investopedia.com/terms/m/maximum-drawdown-mdd.asp).

_Results in BTC and ETH Options Pools_

The details of calculation can be found [here](https://docs.google.com/spreadsheets/d/1XN3lRwnKf__2PBCqHk9wVY-j2cxlJe4kB4JDPvD73x0/edit?usp=sharing).

![](https://assets-global.website-files.com/5f3306add5c511ca4cf17da9/5fcf6d411826482857098bea_4R5CZlcRMYPIrDroCMQmhHN0a_bUKIaC0P9QI34_wIij4dKPA-3nF3tH_Q0H_m5wthIkB_HOC3n5ufY60rkV9OSwEP5u3oDYj8n-lB_PoJcv-Xd6rwPMbEKI1233bDxuXT5LrZ3u.png)

The pool as the collective option seller will be more likely to win in the long run, despite the occasional drawdowns. In the past 12 months, the pool’s net value increased by over 60%, which means a 60% APR in return. Of course, this measurement is using the hypothesis that the pool as collateral is fully utilized. For an average 50% utilization ratio, the expected average APR will be 30%, also with smaller drawdowns.

From the chart above, in case of a relatively long time of unilateral price movement, the pool will suffer losses, especially from March to May 2020 and from October to November 2020 in the test period.

Similarly, with the same methodology, we can simulate the finance performance of a pool for ETH options in the recent 12 months as below. The details of simulation can be found [here](https://docs.google.com/spreadsheets/d/1XDg7DOZ5-7nfO8b9MOuesgJIccOZBxsWecVckOXZxGA/edit?usp=sharing).

![](https://assets-global.website-files.com/5f3306add5c511ca4cf17da9/5fcf6d41f17a0c568de1854b_wZyLz3qQXEaR0IFVs7j3gBiAF3UZoJep0yXrEFZ4XO7-tKsj4GTdwkZRC_rbssAtg_O5pmq5AK2nDWOYdJ9fz9YWk9LLZRelvF81cniJfP86OIyTKgMBIXn6BcrqHvgXPUKxkehq.png)

_Summary_

Collateral pools for options behave differently from better known lending and AMM liquidity pools. The pools provide liquidity and collateral for options, while rewarded with option premiums and undertaking risks. It is possible to lose money in cases of the unilateral market price movement of the underlying assets. But in the long run, it could bring some favorable rewards for the liquidity providers.

**On the Risks in PPO v1.0**

Before ‘jumping into the pool’ or starting trading options on PPO v1.0, it is important to understand the potential risks of the protocol for every user. The liquidity/collateral pool is not risk-free, and participants can lose money.

The risks below are presented in no particular order.

_1. Risks for pool participants_

(1) Options concentration risk

Options are contracts that give the buyers the right to buy or sell assets at a fixed price in a certain period. Therefore, options sellers/writers only have an obligation but paid with a premium (option price). Different from lending money and rewarded with interest, options sellers should deposit collateral for the performance and may lose money.

MASP (Multi-Asset Single-Pool) is the key mechanism Phoenix introduced in the PPO v1.0 model. The liquidity pool or collateral pool acts as the single counterparty for writing, trading, and exercising all of the options contracts. Hence, the pool is the joint options seller. The key to the pool is to have many different options live and dilute the risks exposed by a single option contract.

However, if the options are not adequately diversified, for example, some large option buyers drained the pool’s liquidity, with options of similar terms, the risks for the pool can be quite concentrated. This is more likely when the pool is small.

(2) Unilateral market move risk

The nature of risk-return profiles is different between the option sellers and buyers. It is often regarded that the sellers have limited returns but unlimited risks. One of the goals in MASP is to diversify the ‘unlimited’ risks by pooling all options together. The market is always filled with different expectations and the more conflicting it may be, the more favorable it is for the pool.

However, even when the pool is in a relatively balanced status, in cases of extreme unilateral price moves, the gains in the pool may not be enough to compensate for the losses when option holders exercising the ITM options.

(3) Multi-asset composition risks

PPO v1.0 may have hybrid pools, that accept multiple assets as accepted collateral in the options liquidity pool. The liquidity pool will somehow work like a mutual fund, where after transferring the crypto assets in the pool, you are holding the equivalent shares and entitled to benefits as measured in PPT( Phoenix Pool Token). All the values in the pool are calculated in USD, therefore, the net value of the share, as PPT, will be subject to the changes of the USD value of these collateral assets.

The PPO pools are made of one or several stable coins, whose value is more likely to remain stable and pegged to USD. But for example, in the USDT/USDC hybrid pools, in case that one stablecoin, say USDT, as the collateral asset losses its peg, it may lead to risks and losses to the PPO pool participants, even to the USDC contributors.

(4) Liquidity risks

To maintain the security of PPO, Phoenix Finance introduces the minimum collateral ratio (MCR) in the protocol, to make sure the option contracts are always fully-collateralized.

In cases when the collateral in the pool is fully occupied, pool withdrawal will be paused. Also, the liquidity pool will cease to write new option contracts, until the collateral utilization ratio recovers to be above the MCUR level. Therefore, the withdrawal request will be marked as ‘pending’, until the portal reopens as stated above. The pool participants may have to wait to withdraw their shares of assets out of the pool and suffer from the pool liquidity risks.

Also, to protect against possible flash loan exploits, a pool participant can only quit the pool one hour after making deposits.

_2. Risks for option buyers_

(1) Multi-asset consideration and settlement risks
PPO v1.0 has provided friendly choices for option buyers by setting their customized option terms when buying options, including a selection of currencies to pay. With hybrid liquidity pools, like the USDC/USDT pool, for example, both of the two stablecoins are regarded as the collateral assets. This liquidity pool is the sole counterparty for all options.

When exercising options, the holder is trading against the pool, therefore, the crypto assets as consideration or settlement are transacted from the compositions in the pool. Due to the pool’s multi-asset nature, upon settlement, users will get a basket of tokens that reflects the current composition of these assets (USDC/USDT) in the pool. Therefore, users will get risk exposure to the crypto assets in the pool.

(2) Options of American type
Options on PPO v1.0 are all American types and options holders should exercise in-the-money options manually. Please do remember to exercise your ITM options, or you will lose your profits upon expiration.

_3. Smart contract risks_

Though the code audit of PPO v1.0 is done in Aug 2021 by Peckshield, the whole DeFi is still in the early and experimenting stage. Please keep cautious of the smart contract risks and do not put your life savings inside.

_4. Oracle risks_

Phoenix Finance has partnered with Chainlink, the leading decentralized blockchain data provider for bringing off-chain data to smart contracts on Ethereum and other blockchains. PPO v1.0 applies decentralized price feeds of crypto asset pairs on Ethereum, provided by ChainLink.

Chainlink is a decentralized oracle network that enables smart contracts to securely access off-chain data feeds, web APIs, and traditional bank payments. It is well known for providing highly secure and reliable oracles.

Nevertheless, oracles and external price data aggregation can be considered as a potential risk to the stability of the PPO.

**Making PPO v1.0 Secure**

_Making PPO v1.0 Safe_

In addition to the basic introduction of Phoenix Protocol for Options (PPO) model. There are several important mechanisms elaborately designed for security purposes. It is highly recommended that, before jumping into the pool or trading options on the PPO platform, one should go through these innovative mechanisms, in order to have a better understanding of the PPO model.

PPO v1.0 has been audited by PeckShield.

_1. Minimum Collateral Requirement_

As introduced in the [options guidance](https://docs.phx.finance/options/security/index.md), for the writers/sellers of options, the potential risks are theoretically unlimited. To keep the option contracts secure and capable to perform, there are usually two ways to maintain the full collateralization of the options exposure.

(1) Margin Requirements for Cash Settlement

As widely applied in traditional finance and centralized crypto exchanges, for writers/sellers of options, in other words those who short call or put options, some deposits are required to collateralize the option contracts as margin. The margin ratio is normally 5% to 20%. For example, Deribit’s margin requirement for shorting options is shown [here](https://www.deribit.com/pages/docs/options). This mechanism is capital efficient. It needs less initial margin deposit and provides additional leverage to the sellers, but may require additional capital input, or even lead to liquidation events if the price moves unfavorably. [Cash settlement](https://www.investopedia.com/terms/c/cashsettlement.asp) is often applied with respect to these kinds of options.

(2) Full Collateral for Physical Settlement

Smart contracts and the digital nature of crypto assets provide alternative choices, especially for [physical settlement](https://www.investopedia.com/terms/p/physicaldelivery.asp). The full amount of underlying assets can be physically locked in the smart contracts, in a censorship-resistant way. No one needs to worry about counterparty risks.

However, PPO v1.0 applies a unique Multi-Asset Single-Pool (MASP) model, which pools all the liquidity together to serve as the sole counterparty for writing, trading, and exercising all of the options exposure written from the pool. MASP is the core mechanism and the safety of the pool is always the first priority.

Option sellers’ risks can be relatively higher. MASP pools all the sellers and liquidity, also sometimes referred to as collaterals, together to form a collective counterparty for all options. The point of this pool is to diversify the pool’s risk exposure away from any single type of option. While this tactic largely mitigates the risk exposure for a single seller, it does not eliminate it. The collateralization ratio of the pools should be high enough to safeguard against massive market movements and other black swan events.

As a result, Phoenix introduces the Minimum Collateral Ratio (MCR) requirement for the pool. It is an innovative mechanism designed to control the size of the pool’s total options exposure. The MCR ensures that the options are always over-collateralized.

Due to the multiple asset nature of the pool, according to the liquidity, volatility, and market acceptance of these different crypto assets, The MCR for stablecoins is set to be 120%.

For example, if there are $40,000 USDC in the pool, for BTC puts with $40,000 as the strike price, only an option of value 0.8 BTC can be written.

In other words, for the pool with relatively high MCR, the pooled sellers are de-leveraged, and more security is guaranteed. This is exceptionally important when the pool is relatively small.

_2. Pricing Adjustment Coefficient_

The [classic Black-Scholes options pricing model](https://www.investopedia.com/terms/b/blackscholes.asp) is applied in PPO v1.0 for pricing options and is integrated into the smart contract codes. After inputting certain variables of the Black-Scholes formula via the user interface — like the underlying assets, amount, strike price, and expiration — the remaining required Black-Scholes variables will be inferred and the option premium will be automatically calculated.

One of the main purposes of designing MASP is to make the risks faced by individual option sellers adequately diversified, by collectively pooling all the options writers together. The key is the difference in expectations of crypto holders and the variety of options live in PPO.

However, if the options are not adequately diversified, for example, some large options buyers could drain the pool’s liquidity with options of similar terms. In such a state, the risks for the pool can be quite concentrated. And that risk is much more likely when the pool is small.

Therefore, we have introduced a pricing adjustment coefficient to mitigate the concentration by adding a coefficient for pricing options. It automatically discourages the purchase of options that are already over-weighted in the pool. The coefficient acts as an adjustment multiplier of the Black-Scholes model in pricing options.

In PPO v1.0, the coefficient is decided as follows:

![](https://miro.medium.com/max/875/1*OuqCZKWhXZKh9nNBfLRaJA.png)

The Pricing Adjustment Coefficient changes as follows:

![](https://miro.medium.com/max/1250/1*vMTs8dm-fpIfzG9VtYaPJg.png)

In a nutshell, _If there are more calls than puts, calls are more expensive. And vice versa, if there are more puts than calls written by the liquidity pool, puts are more expensive. The more options written by the pool, the more expensive they are._

_3. Chill Time_

DeFi is still at a nascent experimental stage. We witnessed a number of exploits in the past few months, among which a great proportion are done though [flash loans](https://news.bitcoin.com/defi-flash-loans/). These instant uncollateralized loans enable attackers to make nearly risk-free trials to hack decentralized protocols with little capital requirements and low costs beyond Ethereum gas fees and the time to research the potential exploit.

However, flash loans require that all assets borrowed should be returned before the end of the transaction, in the same mined block.

To protect against possible flash loan exploits in PPO v1.0, a special mechanism called ‘Chill Time’ is designed, during which the options buyers cannot sell or exercise the options, and the pool participants cannot withdraw their assets out of the pool. ‘Chill Time’ for options exercise is set to be one hour. ‘Chill Time’ for pool withdrawal is set to be one day.

_4. Moving Average IV and the IV Surface Mapping_

It is said that trading options is simply trading IV. What is IV? Implied Volatility (IV) is the measurement of the uncertainty of the price movement of the underlying asset. In the Black-Scholes pricing model, it is the key factor in option pricing.

However, the options market of crypto assets is not liquid enough to provide all the IVs for all the potential underlying crypto assets. Even with deeply liquid crypto on the spot market like ETH and BTC, IVs are still somehow quite volatile due to relatively high bid-ask spreads, even for some centralized well-known exchanges like Deribit. For some at-the-money IVs of certain assets with a 5% movement, there could be hundreds of on-chain data inputs per day. That could not accurately trace the market, and also get quite expensive in gas!

Therefore, Phoenix Finance applies the average IV from the most liquid options on the market, which is 1 day, 2 days, and 7 days at-the-money IV, and feeds it into PPO v1.0 by an hourly [moving average](https://www.investopedia.com/terms/m/movingaverage.asp). The protocol then uses this data point as the ‘Anchor IV’ for our DeFi options market.

Based on this ‘Anchor IV’, PPO v1.0 applies the [Stochastic Volatility Inspired (SVI) parameterization model](https://www.math.kth.se/matstat/seminarier/reports/M-exjobb14/140909.pdf), and derives the [volatility matrix or volatility surface](https://www.investopedia.com/articles/stock-analysis/081916/volatility-surface-explained.asp). To be noticed that the whole IV Surface is subjected to changes based on the feed of the ‘Anchor IV’.

Through these innovative mechanisms, PPO seeks to eliminate the abnormal IV movements due to the illiquidity of the market, derive the IV for less liquid options, and be fed by the live IV changes through anchors, according to the market conditions.

All that is to say that we think we’ve figured out a novel way to bring vital IV data into our smart contracts that no other DeFi options protocol does yet.

To sum up, we firmly believe that these mechanisms enable us to provide a robust, safe, and secure environment for crypto enthusiasts to purchase options exposure.

### Leveraged Tokens (PPLT)

**Introduction**

_What is the Phoenix Protocol for Leveraged Tokens (PPLT)?_

PPLT stands for Phoenix Protocol for Leveraged Tokens. It is one of the main products of Phoenix.

PPLT provides a decentralized way for creating and trading decentralized leveraged tokens on cryptoassets, like BTC, ETH, etc., on different chains. These leveraged tokens are powered by no-loss lending pools, where participants can earn interest. All the core functions of token minting, redeeming, taking leverages, borrowing and lending occur on-chain and are managed by smart contracts. It is a permissionless, censorship-resistant, and non-custodial protocol.

PPLT’s goal is to make it simple to trade leveraged tokens in an easy, secure, transparent and decentralized way. It also provides a friendly venue for lenders to earn interest for powering the leveraged positions for the leveraged tokens.

_Why does DeFi Need Leveraged Tokens?_

Traditional leveraged tokens are traded on centralized exchanges, like Binance, FTX, Huobi, etc. These innovative derivative products have attracted great volume since their creation.

Few pieces of research have covered the possibility of decentralization before, yet the Phoenix team believes these products are a winning innovation in the DeFi space.

- On-chain leveraged tokens will be borderless and permissionless. Anyone can get access to the leveraged tokens trading freely without KYC requirements.
- Leveraged tokens have a rebalancing mechanism adjusting their leverages according to the current exposure. Phoenix codes are open-source and all the mechanisms and transactions are public and on-chain. Therefore, better transparency will be guaranteed as compared with centralized exchanges.
- All leveraged tokens will be fully collateralized with underlying crypto assets. There will be no counterparty risks when redeeming.
- All leveraged tokens will be ERC-20 tokens, making it simple to store them in wallets or transfer them between addresses.

**Leveraged Token Basics**

_What Are Leveraged Tokens?_

Leveraged tokens are derivatives giving holders leveraged exposure to cryptocurrency markets, without having to worry about actively managing a leveraged position. They were initially introduced by derivatives exchange FTX, and have since been listed on other centralized exchanges.

For example, the ETHBULL/USD — also known as 3X Long Ethereum Token — is an ERC-20 token with a return that corresponds to three times the daily return of ETH. For every 1% ETH that goes up in a day, ETHBULL rises by 3%.

Leveraged tokens usually offer fixed leverages or leverage ranges through rebalancing mechanisms that maintain the target leverages.

_Rebalancing_

![](https://www.bringyourfinancestolife.com/wp-content/uploads/2017/03/rebalance.jpg)

Rebalancing is a one of the most important elements in the design of leveraged tokens, for it is the mechanism that keeps the leverage at the targeted level.

Let us take a closer look at how rebalancing works, with an example.

You are holding $100 USDC and purchase an ETHBULL (3x) leveraged token. The protocol will automatically borrow $200 in USDC, and trade the total $300 USDC for $300 ETH. Therefore, the $100 ETHBULL (3x) leveraged token is backed by $300 ETH holding and $200 USDC borrowing.

Suppose the price of ETH increases by 20% and the ETHBULL (3x) token price rises to 300*(1+20%)-200=160 before rebalancing. Now, your real leverage becomes 2.25 (360/$160), lower than the target leverage.

As part of the rebalancing process, the protocol will borrow more USDC and purchase extra ETH tokens to shift the leverage back to 3x. In our example, it will borrow another 120 and exchange it for ETH. The total leverage thus becomes (360+120)/160=3x again.

Suppose the price of ETH decreases by 20%, and the ETHBULL (3x) token price decreases to 300*(1-20%)-200=40 before rebalancing. Now, your real leverage would become 6 (240/$40), higher than the targeted leverage.

In this case, the mechanism will sell ETH tokens and repay the outstanding debt to deleverage. In this example, it will sell 120 ETH for USD and payback to the pool. The debt would become 80 and the total leverage would once again be (240-240-240-240-120)/$40=3x.

In other words, the leveraged token will automatically re-leverage in profit and deleverage in loss to restore its target leverage level. If the mechanism works smoothly, the leveraged token will compound profits in the favorable market moves. While in unfavorable market trends, leveraged token holders will never be liquidated, as the deleveraging mechanism will constantly lower the effective leverage level.

**Comparison**

_Differences between Leveraged Tokens and other derivatives_

![](https://z3.ax1x.com/2021/08/03/fCczDS.jpg)

The biggest difference between leveraged tokens and margin trading/perpetuals is that leveraged tokens will rebalance themselves both periodically and when reaching a certain threshold, in order to maintain certain leverage.

This is obviously different from both margin trading and perpetuals - products whose real leverage constantly changes according to price fluctuations, even though traders have designated a specific leverage level upon taking on a position.

You can check [this article](https://coinmarketcap.com/alexandria/article/a-deep-dive-into-leverages-in-defi-borrowing-margin-trading-leveraged-tokens-and-options-finnexus) for more details about leverages in different DeFi products.

**PPLT v1.0**

_Introduction_

The Phoenix Protocol for Leveraged Tokens (PPLT) v1.0 is a decentralized and non-custodial protocol for creating and trading decentralized leveraged tokens, which are powered by lending pools. The protocol is accessible through a joint interface that supports multiple blockchains.

Phoenix’s Leveraged Tokens give holders leveraged exposure to cryptocurrency markets, without having to worry about actively managing a leveraged position. The rebalancing mechanism maintains the holders’ leverage exposure at a fixed level, no matter how the underlier’s price moves. Therefore, token holders will never get liquidated - a key difference compared to trading on margin or using perpetuals.

Phoenix leveraged tokens are asset-backed tokens, NOT synthetic assets. They always have 100% collateralization, in collaboration with other decentralized exchanges. Real cryptoasset borrowing and transactions are conducted through smart contracts to back the value of the tokens. Thanks to the on-chain rebalancing mechanism, a leverage range close to 3x is maintained for the holders. Anyone can monitor and verify the collateral and leveraged positions embedded in the tokens at any time in a transparent way.

Lending pools power the tokens’ leverage. When leveraged tokens are created, they automatically borrow an equivalent amount of cryptoassets from the pools, and trade to get leveraged exposure. Pool participants will earn passive interest returns.

_Basic Modelling Structure_

![](https://z3.ax1x.com/2021/08/03/fCgD2t.md.jpg)

_Lending Pools_

_Concepts and Utilities_

Lending pools power and rebalance the leverage for the "Bull" and "Bear" tokens.

For Bull tokens, a stablecoin pool is created. The single pool can lend assets to bull token contracts with different underlying assets. For example, the BTCBULL (3x) token and ETHBULL (3x) token share the same stablecoin pool. When new bull tokens are minted or rebalanced, borrowing and lending transactions take place within the protocols.

For Bear tokens, separate pools with underlying assets are created to power different tokens. For example, the BTCBEAR (3x) tokens will borrow WBTC and sell to take short positions on the market, therefore, a WBTC pool provides the necessary leverages when minting or rebalancing.

In the PPLT v1.0, the standard interest rate is fixed, provided that the lending pools are not fully utilized. Interest is collected periodically from the leveraged tokens, distributed to and shared by all pool participants automatically.

_Pool Shares_

Similar to most pooled models in DeFi, the shares of the PPLT lending pools are tokenized as PPT, standing for “Phoenix Pool Token”.

PPLT lending pools are created when individual liquidity providers contribute liquidity by staking their crypto assets in the pool. The liquidity providers receive a pool token - the PPT - which represents their share of ownership in the pool.

In the PPLT v1.0’s lending pools, Interest is not distributed; instead, users earn interest simply by holding PPT. Over time, each PPT becomes convertible into an increasing amount of the asset, even while the number of PPTs in a wallet stays the same.

_Pool Net Value and FPT Value_

_What Is Pool Net Value?_

The Pool Net Value measures the monetary value of all assets and the outstanding lending amount currently in the lending pool. The Pool Net Value is also regarded as the Total Value Locked (TVL) in the lending pools.

_What Affects Pool Net Value?_

Let us take the ETH pool for example. The total Pool Net Value (PNV) in USD is affected by the following factors:

1) ETH deposits increase the PNV; 2) ETH withdrawals decrease the PNV; 3) Receiving interest from lending assets to leveraged tokens increases the PNV; 4) Changes in the USD value of ETH increase or decrease the PNV.

_PPT Value_

After a user deposits crypto assets into the pool, assets are collateralized, and the holders are entitled to the benefits of having a fraction of the lending pool. PPT is minted and delivered to the users, representing a pro-rata share of the pools.

The net value of PPT is calculated using the Pool Net Value (as defined above) and dividing it by the total number of PPT tokens.

Net Value of FPT = Pool Net Value / No. of FPT

Due to the no-loss characteristics of the lending pools, the PPT value will be ever-increasing, if measured in pooled assets. Specifically, the PPT value of the USDC pool is ever-increasing measured in USDC, and the PPT value of the ETH pool is ever-increasing when measured in ETH.

_Basic Interest_

Participants in the lending pools can earn interest from lending, which powers the tokens’ leveraged position. Interest is collected and distributed in the pool automatically through smart contracts, which leads to an increase in the PPT value over time, measured in terms of pooled assets.

Unlike most DeFi borrowing and lending protocols, the basic interest rate for borrowing and lending activities is a fixed amount in PPLT v1.0. For the borrowers, the borrowing rate is fixed and not subjected to changes, provided that the pool is not fully occupied.

For lenders, the higher the utilization rate of the pool, which means the larger proportion of the pooled assets is involved in lending, the higher APY the pool will have.

_Interest Adjustment Mechanism_

When the lending pools are fully occupied, it is possible the targeted leverage level cannot be achieved when rebalancing, due to a lack of funds to borrow from the pools. In this case, the rebalancing could temporarily fail.

To address this issue, in order to incentivize more contributors to join the specific lending pool that is fully utilized, the interest rate for borrowing and lending will be temporarily increased, which in turn will attract lenders. If the pool is still not big enough to cover the amount needed for the tokens’ rebalancing, the interest will be further increased, until the targeted leverage level is reached.

Once the targeted leverage is reached, the rate will move back to the basic interest level.

_Rebalancing Mechanism_

Rebalancing is a very important mechanism to keep the leverage at the targeted level. There are two instances when leveraged tokens will rebalance themselves.

_Scheduled Rebalancing_

Phoenix leveraged tokens "rebalance" themselves periodically, so they can keep the target leverage. At every rebalancing occasions, each leveraged token reinvests profits if making any, and if losing money, sells off part of its position to lower the leverage to avoid liquidation.

In the PPLT v1.0, the targeted leverage range is set and periodically, the protocol will check if the real leverage is within the targeted range level. If the real leverage is lower than the minimum threshold or higher than upper threshold, the rebalancing will be triggered.

For example, let us imagine that a user holds 1 unit of ETHBULL (3x) token with an initial cost of 100. The price of ETH increases by 15% and the token price rises to 145 before rebalancing. Now, the holder’s leverage becomes 2.38 (345/345/345/345/145), lower than 2.5, e.g., the targeted leverage.

During the scheduled rebalancing, the protocol will borrow more USD from the stablecoin pool and purchase extra ETH tokens to shift the leverage back to 3x. In our example, the protocol would borrow another 90 and exchange it for ETH. The total leverage would thus become 3 (435/$145) again.

Following the example above, what would happen if the ETH price decreased by 15% and the token price dropped to 55 before rebalancing? The holder’s leverage would become 4.64 (255/55), higher than the targeted leverage, e.g., 3.5. During the rebalancing process, the protocol would then sell ETH tokens and repay the outstanding debt to deleverage. In our example, the protocol would sell 90 ETH for USD and payback to the pool. The total leverage would once again be 3X (165/165/165/165/55).

For Bear leveraged tokens, the rebalancing process is similar to the examples mentioned above.

_Temporary Rebalancing_

One interesting aspect of leveraged tokens is that their holders never have to worry about liquidation, as the product automatically deleverages itself.

However, it is important to be aware that a temporary rebalancing may be needed when an unfavorable price movement occurs, especially if this happens in a short period of time.

For example, for ETHBULL (3x) tokens, if the ETH price were to drop by over 33%, the token value would go ‘negative" — something akin to getting liquidated. In such cases, the rebalancing mechanism needs to be triggered to deleverage the tokens, even if the time for a scheduled rebalancing has not yet arrived.

In the PPLT v1.0, for the 3x leveraged tokens, the threshold to trigger a temporary rebalancing is set to be a 20% unfavorable movement against the past underliers’ rebalancing price. Bull and Bear leveraged tokens with different underlying assets will have independent triggers to activate a temporary rebalancing.

The temporary rebalancing process itself, however, will be the same as the scheduled rebalancing.

_Termination_

If the temporary rebalancing is unsuccessful, no matter the reason, the protocol will initiate a termination process once the price gets to a 30% unfavorable movement.

Termination is similar to a liquidation process, with all the terminated leveraged tokens being redeemed and burnt. After triggering a series of transactions on Dexes, the debts will be paid back, outstanding interest and fees will be deducted, and the remaining balance will be claimable for the leveraged token holders.

**Risks**

_Price slippage and transaction fees in purchasing and rebalancing_

When Phoenix leveraged tokens are minted, as they are backed by assets, a series of transactions need to take place with decentralized exchanges. Similarly, during rebalancing, transactions need to be triggered in order to maintain the targeted leverage level.

Traders may face price slippage and transaction fees when making these transactions, with the degree of slippage and transaction costs depending on the depth of the market liquidity in the trading pairs and the volume of the transaction. Larger orders when purchasing or redeeming, and a greater volume of transactions when rebalancing may lead to a higher price slippage and transaction costs, thus having a negative influence on the tokens’ financial performance.

_Risks associated with maintaining leverages_

The fact that leveraged tokens maintain their leverage exposure to a fixed level or range may lead to unexpected outcomes, especially compared with margin trading. (From this perspective, please remember that leveraged tokens are commonly regarded as an instrument to trade rather than hold.)

This is because when bull leveraged tokens have gains, they will borrow and reinvest to increase their long positions. And if bear leveraged tokens have gains, they will borrow and sell more to increase their short positions.

A practical example will help clarify how the behavior of leveraged tokens differs from standard leveraged trading. Let us compare ETHBULL (3x) with trading a 3x ETH position on margin. If ETH goes up one day and then up again the next, ETHBULL will do better than a standard margin position, because it will have reinvested the profits from the first day back into ETH. However, if ETH goes up and then falls back down, ETHBULL will do worse, because the reinvestment during rebalancing increased the exposure, compared with margin trading.

Therefore, it is possible that even if the underlier’s price increases, the leveraged token’s net value drops. As shown in the table below, even though over two days the price of ETH rises from $2000 to $2024, the value of leveraged tokens decreases, due to the re-leveraging on day 1.

![](https://z3.ax1x.com/2021/08/03/fCgD2t.md.jpg)

| **Time**  | **ETH Price ($)** | **ETH Price Change** | **Leveraged Tokens ($)** | **Margin Trading ($)** |
|-------|---------------|------------------|----------------------|--------------------|
| Day 0 | 2000          |                  | 2000                 | 2000               |
| Day 1 | 2200          | 10%              | 2600                 | 2600               |
| Day 2 | 2024          | -8%              | 1976                 | 2072               |

_Risks associated with transaction failure_

Dexes run on public chains and there may be unexpected scenarios leading to transactions failure, like network conjunctions, volatile price movement or platform misfunction. Collaboration of protocols may lead to the composability of risks. This may in turn cause a rebalancing failure, making the protocol unable to maintain the targeted leverage. In extreme cases, if the market makes a dramatic unfavorable movement, the lending pool may suffer a value loss due to the negative value in leveraged tokens.

_Smart contract risks_

The whole DeFi ecosystem is still in an early experimenting stage. Please always be alert to possible smart contract risks and only invest what you can afford to lose.

_Oracle risks_

Phoenix has partnered with Chainlink, the leading decentralized blockchain data provider, to bring off-chain data to smart contracts on Ethereum and other blockchains. The PPLT v1.0 applies decentralized price feeds covering cryptoasset pairs provided by Chainlink.

Chainlink is a decentralized oracle network that enables smart contracts to securely access off-chain data feeds, web APIs, and traditional bank payments. It is well known for providing highly secure and reliable oracles.

Nevertheless, oracles and external price data aggregation can be considered as a potential risk to the stability of the PPLT if any unforeseen issue arises.

**Lev Tokens Live**

Leveraged Tokens Live on Wanchain (Updated on 2021/10/21)

| **Name**     | **Address**                                |
|--------------|--------------------------------------------|
| WAN_BULL 3X  | 0x7fc47e269d29094d0c10a70fddc0fee73a068a4b |
| WAN_BEAR 3X  | 0x031bd723b3183c825219382ab61032624c4e8d94 |
| XRP_BULL 3X  | 0xB3acdEc0b613631c89A7B1Af6053eEeb2de3F210 |
| WASP_BULL 3X | 0xBFE9c79831e29eb2aA2bCBd9D93195A9bAe28255 |

**Phoenix Rewarding and Boosting System**

In order to achieve sustainable ecological development, Phoenix Finance's mining mechanism aims to reward contributors in a long-term and stable manner. These contributors include but are not limited to users who provide liquidity for Phoenix DeFi options and leveraged tokens, those who provide liquidity on Dexes, reciprocal rewards for partners, and more. These rewards will be distributed from the PHX community reserves.

_Incentives for Providing Liquidity for Phoenix Products_

Liquidity is the key to any DeFi protocol. Decentralized derivatives need deep liquidity to power the trading volume and lower slippages, and the product liquidity mining reward will be a long-term incentive measure.

_Pools_

Phoenix Finance is launching the following liquidity pools for options and leveraged token products with cPHX as incentives:

- USDC/USDT options pools on Polygon, BSC and Wanchain
- USDC lending pools for leveraged tokens on Polygon and BSC
- WBTC lending pools for leveraged tokens on Polygon and BSC
- ETH lending pools for leveraged tokens on Polygon and BSC

For the options pool, other stable coins will be added as collateral assets in the future. For any newly added leveraged token, there will be an additional lending pool with its related underlier. For instance, a $MATIC lending pool will be established when launching $MATIC leveraged tokens and so forward.

_Mining Incentives_

_Basic Rewards_

Basic rewards are incentives for liquidity providers contributing collateral assets. When a user deposits collateral assets into the relevant pools, he/she will receive pool tokens, representing a share of the pool and be rewarded accordingly. Rewards will be calculated in each block.

Basic Rewards = Total Basic Rewards × Share of the Pool.

_Boosted Rewards_

Boosted rewards are incentives for miners staking PHX or cPHX in the contracts, meaning users can stake PHX or cPHX in the boosting contracts to enhance the basic mining rewards.

Boosted Rewards = Basic Rewards × Multiplier

The more PHX or cPHX is staked, the higher the multiplier will be. Likewise, the longer the time PHX or cPHX is staked for, the more substantial the returns.

The multiplier is derived by the following formula.

multiplier=[0.004×(N/500)^0.3 + 0.0067×(N/500)^0.25 ]×(T-1)+(N/500)^0.05

In which N is the effective staking amount, and T is the number of months in lockup. Staking 1 PHX or 1 cPHX means N=1.

Please note that you have to stake enough PHX or cPHX so that N is no smaller than 500, to have an effective multiplier, which is greater than 1.

For example, if locking your tokens for 6 months, the multiplier chart against the PHX locked amount will shape as follows:

![](https://z3.ax1x.com/2021/08/08/flay1U.png)

For example, if locking 50,000 PHX tokens, the multiplier chart against the lock time will shape as follows:

![](https://z3.ax1x.com/2021/08/09/f13WO1.png)

Please also note that the boosting effect will decrease on a monthly basis. E.g., a user staking PHX for 6 months will have a 5-month boosting effect after 1-month period. However, one can always increase his/her lockup time by one month to have a constant boost in every month.

_Miscellaneous_

_Boosting designation_

If a user has boosted rewards in a pool, the reward enhancement can be transferred to other pools at any time. You can transfer the multiplier or the boosting re-designation by moving the locked PHX or cPHX (vePHX) between pools. A partial transfer is also possible.

For example, Alice is contributing USDC and ETH in the USDC and ETH lending pools for leveraged tokens. She is also staking all of her PHX holdings and boosting the rewards in the USDC lending pool. At any time, she may choose to designate part or all of the vePHX as the booster for the ETH pool. After the re-designation, the boosting in the USDC pool will decrease, while the boosting in the ETH pool will increase.

_cPHX_

All incentives are distributed in cPHX, or convertible PHX. cPHX can be converted to PHX at an equal ratio. Once converted to PHX, the cPHX is burned and it entitles the holder to claim ⅙ of the PHX every 30 days. The first ⅙ of the PHX will be released immediately. cPHX can be also staked as a booster, with the same boosting effect as PHX.

_vePHX_

Both PHX and cPHX, once staked as reward boosters, are called vePHX. The vePHX lock-time is the same in each address, even if they are powering different pools. In other words, if a user adjusts the vePHX lock period in a pool, the lock time in all pools will be adjusted. The vePHX lock time can only be extended, not shortened.

_Boosting Impact_

vePHX only affects the rewards after boosting and does not change the basic rewards. The basic rewards solely depend on the amount of collateral assets one stakes. The boosting will not affect the withdrawal of the collaterals.

The advantage of this mechanism is that users can flexibly adjust the pools they intend to boost in, according to the change of the basic rewards.

_Returns in Native Collateral Assets_

In addition to PHX rewards, in the long run, the native returns directly generated by the protocols are essential.

_Options_

Options pools collect liquidity from contributors, as the collective option sellers, who earn premiums from buyers. These premiums automatically accrue in the liquidity pools and accumulate over time. (Please notice that being an options seller entails risks, though these are diversified by varieties of outstanding options. Please check the product paper for more details.)

_Leveraged Tokens_

The pools powering leveraged tokens are lending pools. They generate interest income by lending assets to users who buy leveraged tokens. The income directly accumulates in the pools, which is reflected in the value of LP tokens. Please check the product paper for more details.

_Total returns from the Phoenix Protocols_

*Returns in the options pools = Options Premiums (in collateral assets) + Basic Mining Rewards (in cPHX) + Boosted Rewards (in cPHX)

Returns in the lending pools for leveraged tokens = Interest for lending assets (in collateral assets) + Basic Mining Rewards (in cPHX) + Boosted Rewards (in cPHX)*

_Incentives for Providing Liquidity for PHX pairs in Dexes_

There are incentives for providing liquidity for PHX pairs on Dexes on all four chains - Ethereum, Polygon, BSC and Wanchain. Rewards are distributed in cPHX. It suffices to stake the relative LP tokens in the mining contracts to be entitled to the mining rewards.

Mining rewards on Dexes = Total Basic Rewards × Share of the Liquidity Pool.

However, please note that these mining incentives are not eligible for boosting.

_Reciprocal Rewards for Ecological Partners_

Phoenix Finance intends to establish deep cooperative relations with relevant DeFi partners, providing mutually beneficial mining incentive schemes. These incentives will be drawn from the community reserves. Please follow our official channels for the latest announcements.

_Final Notes_

The parts above constitute Phoenix's rewarding and boosting system. Since Phoenix Finance implements multi-chain deployment, the reward mechanisms do not specifically refer to one single chain, but in a more general manner across all chains. Specific mining rewards will be determined according to the live products on each chain.

## Phoenix Token (PHX)

**PHX Addresses**

The PHX token is the protocol token for the entire suite of Phoenix protocol clusters. It serves a variety of purposes including governance, voting, liquidity mining, reward boosting and more.

- PHX token is now live on Ethereum, Polygon, BSC and Wanchain.

| **Public Chain**     | **Address**                                |
|--------------|--------------------------------------------|
| PHX@Ethereum | 0xAeC65404DdC3af3C897AD89571d5772C1A695F22 |
| PHX@Polygon  | 0x9c6bfedc14b5c23e3900889436edca7805170f01 |
| PHX@BSC      | 0xac86e5f9bA48d680516df50C72928c2ec50F3025 |
| PHX@Wanchain | 0xF17c59bF0f6326dA7A8cC2CE417e4F53a26707bd |

- cPHX token is the convertible PHX, as the incentives for mining rewards. After tranferring cPHX into the conversion contract, 1/6 PHX can be claimed in every 30 days. The first 1/6 will be released immediately.

| **Public Chain** | **Address**                                |
|------------------|--------------------------------------------|
| cPHX@Ethereum    | 0xBdD50c7B6c871D9aFB278445d5b74fDc4705a234 |
| cPHX@Polygon     | 0x54a02fd4aefc77aa97cd3d30322f3e7a7d875a27 |
| cPHX@BSC         | 0xd8fa6921b24ab1cd52ab553d1f99aaedc321e562 |
| cPHX@Wanchain    | 0xD8Fa6921b24AB1cD52ab553d1F99aAEdc321e562 |

**Distribution**

The total supply of PHX token is 176,406,168. Please find [the details here](https://etherscan.io/token/0xaec65404ddc3af3c897ad89571d5772c1a695f22) on Etherscan.

It is native on Ethereum and can be bridged to Polygon, BSC and Wanchain with decentralized bridges.

Please find the major token holders and contracts' balances here (on 2021/8/26):

| **Type**                | **Address on ETH**                         | **Balance on 2021/8/26** | **Percentage** |
|-------------------------|--------------------------------------------|--------------------------|----------------|
| Total supply            | 0xaec65404ddc3af3c897ad89571d5772c1a695f22 | 176,406,168.00           | 100%           |
| Community Reserves      | 0x69a5d86ab428dcc0a91cd47acbfdae43690947b8 | 56,484,710.14            | 32%            |
| Insurance Reserves      | 0x95b4ceb578500bdf6c640a02c2f20481f496d9bb | 25,000,000.00            | 14%            |
| Team Reserves 1         | 0x96ef63fedb08cffc92fb701e7f8a3569a10a53c0 | 20,898,150.00            | 12%            |
| BSC and Wanchain Bridge | 0xfceaaaeb8d564a9d0e71ef36f027b9d162bc334e | 16,072,631.50            | 9%             |
| Polygon Bridge          | 0x40ec5b33f54e0e8a33a975908c5ba1c14e5bbbdf | 12,068,258.18            | 7%             |
| Management Reserves     | 0xad66cdf6462269b678fb5fc9469e5383b31ae2cc | 9,700,000.00             | 5%             |
| Institution Reserves 2  | 0x4ea555693ba302d4175cc956063447bb63511cab | 8,008,325.00             | 5%             |
| cPHX Converter          | 0x663e0657202588c0eabd8bd6da67d87d52d3e851 | 3,742,832.57             | 2%             |

| **Type**                         | **Address on Polygon**                     | **Balance on 2021/8/26** |
|----------------------------------|--------------------------------------------|--------------------------|
| PHX in the boosting contract     | 0x22a4d738467ce153f8a16154a968ccb3be0a0699 | 5,484,240.00             |
| PHX in the compensation contract | 0x5bc9de01a94e89a368dc95684603ba72cc0090ef | 279,706.00               |
| cPHX Converter                   | 0xd61bc69e0ccd37c3b38dabb42162525b69be60ab | 2,607,079.00             |

| **Type**                         | **Address on BSC**                         | **Balance on 2021/8/26** |
|----------------------------------|--------------------------------------------|--------------------------|
| PHX in the boosting contract     | 0x649651fc6cf57eb8bc0ad0bd8dd13649a39bf9e7 | 2,532,017.00             |
| PHX in the compensation contract | 0x481fA2731e503eF7d548b98285165eb0C81384F4 | 120,483.00               |
| cPHX Converter                   | 0x51e5079695f958128fdd6bd7ecbf7db06bdd7267 | 2,316,707.00             |

| **Type**                         | **Address on Wanchain**                    | **Balance on 2021/8/26** |
|----------------------------------|--------------------------------------------|--------------------------|
| PHX in the boosting contract     | 0xeeafc3c679f17165c245aeb6252a1101d7c451a3 | 534,666.00               |
| PHX in the compensation contract | 0x18e243aef86b4fF3De99Cd0eE1E4333Ca5DF56E5 | 1,097,072.00             |
| cPHX Converter                   | 0x6563c5f2affc49e186eca79cb0ea6f91a9c6ecba | 1,266,432.75             |

**Crosschain**

PHX and cPHX token are live on Ethereum, Polygon, BSC and Wanchain. PHX and cPHX holders can move the tokens freely among these chains.

The following example is how to cross PHX tokens among different chains. cPHX cross-chain will follow the same steps, by selecting cPHX in the interfaces.

_Ethereum <-> Polygon_

The portal for moving between Ethereum and Polygon is [https://wallet.matic.network/bridge/](https://wallet.matic.network/bridge/).

1) After connecting your wallet, it will direct you to the following page. 

![](https://z3.ax1x.com/2021/08/02/fSQi1U.png)

2) Press the 'Move funds from Ethereum to Polygon' button, and you will see the bridge interface as below.

![](https://z3.ax1x.com/2021/08/02/fS1dOg.png)

3) Select 'Phoenix Token' from the drop-down menu. 

![](https://z3.ax1x.com/2021/08/02/fS1Bwj.png)

4) Press transfer button and it will trigger the cross-chain transaction. It may take a few minutes to complete.

![](https://z3.ax1x.com/2021/08/02/fS16f0.png)

![](https://z3.ax1x.com/2021/08/02/fS1yYq.png)

_Ethereum <-> BSC <-> Wanchain_

Wanchain is providing decentralized bridges for moving assets across Ethereum, BSC and Wanchain at [https://bridge.wanchain.org/](https://bridge.wanchain.org/).

1) Select PHX from the drop-down menu at the top right as below. 

![](https://z3.ax1x.com/2021/08/02/fS1579.png)

2) You will get to the following interface, then select the desired chain you intend to bridge your PHX tokens to. Then press 'convert'.

![](https://z3.ax1x.com/2021/08/02/fS1bp6.png)

3) After connecting your wallet, it will direct you to the following page. Input your destination address and amount in the blanks and confirm the transaction.

![](https://z3.ax1x.com/2021/08/02/fS17fx.png)

4) It may take a few minutes to complete the cross-chain transactions. 

![](https://z3.ax1x.com/2021/08/02/fS3P9P.png)
