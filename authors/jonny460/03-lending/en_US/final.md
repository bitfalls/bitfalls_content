Decentralized finance (DeFi) through Ethereum applications is [booming](https://defi.academy).

As the ecosystem continues to mature and investors look to consolidate following 2018’s brutal bear market, some hugely innovative steps have been taken to give holders and investors new ways to manage their money. Traditional financial instruments let holders borrow, lend, hedge, and leverage in pursuit of a return, and such options are beginning to become a reality on the blockchain too.

DeFi applications also target those around the world who are excluded from some aspects of the financial system. While many require some collateral from the user, the services we will discuss don’t require a credit check and there is no middleman involved. This is where smart contracts come into their own and demonstrate the real power of decentralized financial systems. In this article we’ll be focusing on lending and borrowing, and in particular why an institution or investor would want to delve into this complex area.

There is over $500m USD locked up in financial smart contracts at the time of writing, with the vast majority in borrowing and lending applications. To understand the options available, we’ll also run through some of the big Ethereum DeFi applications - Maker, Compound, Dharma, and dYdX. It's worth understanding the differences in these protocols and applications, subtle as they are, as their differences offer varying possibilities for borrowers and lenders.

## Maker

We ran through [Maker](https://makerdao.com/en/), and its stablecoin Dai, in a [previous article](https://bitfalls.com/2019/04/30/ethereum-stablecoin-primer-whats-currently-out-there/), so this will be a quick recap. We can’t talk about DeFi without mentioning Maker, the most used DeFi application out there in terms of value locked in. Over 1.6m ether is currently parked in smart contracts as collateral for Dai loans, which is comfortably over 1% of the total Ether supply.

As mentioned, Dai is a stablecoin with a peg that targets a value of 1 US Dollar. Unlike other stablecoins like Tether that are (partially) backed by dollars in the bank, Dai is backed by ether deposited by users. You can borrow Dai by sending your ether to a smart contract called a collateralized debt position (CDP), a process explained in [this article](https://bitfalls.com/2019/01/18/make-your-crypto-work-for-you-how-to-create-dai/). The CDP smart contract keeps everything in balance by minting and burning Dai as it is borrowed and returned.

Dai loans are overcollateralized (i.e. you get less than the monetary value of your ether in Dai when you use a CDP, and the ratio of ether to Dai must be higher than 125% to avoid losing your collateral), which protects the value of Dai should ether decrease drastically in price. You deposit a fluctuating asset and borrow a stable one in return. In comparison to the other services discussed here, Dai is the only asset you can currently borrow through Maker, although a [multi-collateral platform is in the works](https://medium.com/makerdao/update-the-road-to-multi-collateral-dai-2d4c48092270).

So, why lock your ether up? If you think the value of ether is going to increase, borrowing Dai against it means you can still use some of the monetary value of that ether for other purposes, while the underlying asset remains yours. You have liquidity while still holding your ether, and can pay off the CDP and, in essence, buy ether back at a knockdown price.

While entering into a CDP is a great way to get some liquidity for other purposes while still holding, other options exist for simply generating interest on the cryptocurrency you hold. Earning interest is something that anybody with a savings account can understand, but to achieve this on the blockchain, some newer services uses short term loans which allows users to lend their cryptocurrency.

## Compound

[Compound](https://compound.finance) is a collection of smart contracts, accessed through an interface, that acts as a decentralized money market. Traditionally, money markets are used by financial institutions to make short term loans on assets with high liquidity. Those participating can put capital they don’t need at that moment to work, adding it to a shared pool of resources which are then loaned out to those who require it, with an interest fee.

  

With Compound, users can deposit assets into a shared liquidity pool- a decentralised money market. On doing so, users receive tokens that represent their balance in the protocol (e.g. cEth, cDai, cUSDC, and so on). As time passes, each cToken becomes redeemable for a greater amount of its corresponding token. The protocol algorithmically determines the interest rates based on supply and demand in the market at that time, and interest is paid to lenders after each ethereum block (so every 15 seconds), with no gas fees. The user is free to withdraw their ether from the pool at any time, along with the interest accrued in that time- there are no specified loan terms.

  

You can borrow or lend Ether, Dai, USD Coin, Augur, 0x, and Basic Attention Token through Compound. Interest rates for lenders is virtually nothing for ether to close to 10% for Dai at the time of writing. For borrowers, you can get an ether loan for 2.5% APR, and a Dai loan at 14% APR. Similar to other services, Compound requires an overcollateralization of 150%. See [here](https://bitfalls.com/2019/01/22/make-your-crypto-work-for-you-earning-interest-on-crypto-loans/) for a guide of how to loan out Dai to start generating interest. 

  

<h2>Dharma</h2>

  

[Dharma](dharma.io) is a newer player, having launched in April 2019. Like Compound, Dharma exists as a series of smart contracts that govern the lending and borrowing of cryptocurrency. At the moment, Dharma supports Ether, Dai and USD Coin.

  

One key difference between the protocols is that Dharma facilitates peer to peer lending, against Compound’s shared liquidity pool. This means that a user lending their funds will only gain interest when that money is loaned out to another user who has put up some collateral, although Dharma is working to implement a new smart contract that promises [instant matching](https://blog.dharma.io/introducing-instant-matching-9c54ca0d2a66)

  

Another key difference is in the terms of the loans. While in Compound users can pay their loan off or withdraw their funds from the liquidity pool at any time, Dharma offers short fixed-term loans with a fixed rate. That means the lender can’t withdraw their funds until the loan period is up, and the borrower must repay by that date or face losing their collateral. Like Maker and Compound, Dharma requires overcollateralization, and if the loan-collateral ratio falls below 125%, the smart contract begins liquidating the collateral to ensure the lender gets their full amount back plus interest. You can borrow and lend ether, Dai, and USD Coin through Dharma, and [DeFipulse](https://defipulse.com/dharma) reports that over 80,000 ether is currently locked up in the Dharma system.

  

For these systems to work, they need both demand for loans and holders willing to supply them. In order to do this, Dharma was previously subsidizing the process, hoping it will work as a loss leader. This means that lenders received more interest than borrowers pay on their loans, with Dharma topping up interest rates for lenders to encourage more people to make use of this facility. Now, the interest rates are equal for lenders and borrowers- you can borrow or lend ether, Dai, or USD Coin for 1%, 8%, or 6% APR respectively. While gas fees aren’t an issue for Compound, which uses internal transactions, Dharma subsidize gas fees on their loans.

  

<h2>dYdX</h2>

  

[dYdX]([https://dydx.exchange/) is similar to Compound in that its smart contracts run a liquidity pool rather than peer to peer lending, with algorithmically-set interest rates. The major difference is that dYdX is focused on a specific use case for this type of lending and borrowing- margin trading. Margin trades allow traders to gain from decreases in the price of an asset (short selling), or from increases (leveraged long positions). dYdX support ether, Dai, or USD Coin.

  

A trader trigger this process by sending a loan offer, a buy order, and the amount of buy, to one of dYdX’s smart contracts. The smart contract then transfers the deposit to itself, and taps into a decentralized exchange, usually 0x, to sell the asset at the buy price specified by the trader. The smart contract holds the deposit and assets that were gained in the sale of the loan on the exchange, until the trader decides to close the position at which point they receive their loaned amount, plus any profit. A fairly complicated process, but it allows entirely decentralized margin trading to be accomplished, without leaving dYdX’s platform.

  

<h2>Use cases, benefits, and risks</h2>

  

What kind of participants are using these services? Borrowers are anyone from quantitative trading desks or hedge funds to lone traders and savers. Some use their borrowed assets for margin trading, short selling, arbitraging and hedging portfolio risk. Lenders can be anyone with a positive long term outlook on the value of the assets they are holding. With lending rates generally highest for Dai, it is possible to achieve an annual return on savings that exceeds the majority of saving accounts with traditional financial providers

  

Decentralizing some of the process described above, like generating interest or taking out loans, offers tangible benefits for all involved. The biggest advantage is the transparency. Many of the smart contracts developed by market participants are open source, and information about loans taken out is easy to find and free to access. In addition to that, lending services like Compound determine the interest rates by the demand among users, although others still control rates centrally (e.g. Dharma).

  

The other major advantage is the efficiency of the process- you can take out a loan in minutes, receive your funds right away, without going anywhere near a credit agency. The only disadvantages versus traditional financial routes to borrowing money are those that usually arise as part of working in the blockchain space. Firstly, there is typically no insurance should something go wrong. This is a particular danger as transactions cannot be reversed on the blockchain so any flaws in smart contracts could have serious financial consequences. Also, there are few bridges for interfacing with the traditional financial system, and exchanging large amounts of cryptocurrency for fiat currency is still difficult for most (although the addition of USD Coin to these platforms in recent months is hoped to increase interest from traditional financial institutions).

  

The other big risk for a participant is price. All of the services we’ve discussed use overcollateralization to protect against big negative price movements. At best, these movements devalue the ether you’ve locked away as part of your CDP or other collateral mechanism, and, at worst, your collateral will be liquidated to cover your debt. Some new services, like [Decenter’s CDP Saver](https://blog.decenter.com/2019/04/29/introducing-cdp-saver-cdp-management-and-protection/), are springing up to give loan holders better visibility over when their CDP might be in danger.

  

The fact that Ethereum is the go-to platform for DeFi makes perfect sense, given its status as the biggest programmable blockchain out there and the functionality available through smart contracts. Even by Ethereum’s standards this is a young and developing industry that will go through many tweaks and shifts, but the advantages offered for borrowing and lending through these applications are already clear. Continuing to mitigate the great risks- delivering better decentralization and transparency, and building insurance mechanisms to protect against smart contract risk- will help lending and borrowing protocols to keep growing.

[Maker]: https://makerdao.com/en/

[previous article]: https://bitfalls.com/2019/04/30/ethereum-stablecoin-primer-whats-currently-out-there/

[this article]: https://bitfalls.com/2019/01/18/make-your-crypto-work-for-you-how-to-create-dai/

[multi-collateral platform is in the works]: https://medium.com/makerdao/update-the-road-to-multi-collateral-dai-2d4c48092270

[Compound]: compound.finance

[here]: https://bitfalls.com/2019/01/22/make-your-crypto-work-for-you-earning-interest-on-crypto-loans/

[Dharma]: dharma.io

[instant matching]: https://blog.dharma.io/introducing-instant-matching-9c54ca0d2a66

[DeFipulse]: https://defipulse.com/dharma

[dYdX]: https://dydx.exchange/

[DeCenter’s CDP Saver]: https://blog.decenter.com/2019/04/29/introducing-cdp-saver-cdp-management-and-protection/
