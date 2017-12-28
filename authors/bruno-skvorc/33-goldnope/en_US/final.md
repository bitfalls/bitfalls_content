These days, transaction fees in [Bitcoin][cc] (BTC) [can reach][fees] up to $60 regardless of the amount that's being sent. The [protocol][bc] regularly has over [200,000 unconfirmed transactions][unconf] in the queue which can sometimes stay stuck for up to a week. More and more companies and payment service providers are [moving to alternatives][bchalt] or [abandoning the crypto boat altogether][steam].

Bitcoin has become less usable than traditional SWIFT transfer. Even [Bitcoin maximalists][max] are no longer considering it a transactional medium or a replacement for fiat. They are now looking at it from a _Store of Value_ perspective - something akin to gold.

In this article, I'll argue for why I think Bitcoin can never become digital gold.

## 1. Gold does not crumble when moved

If you have some gold and move it from one end of the table to the next, it'll stay in one piece. With the transactions at the level they're at now, it's like the gold is crumbling.

![Crumbling gold](https://bitfalls.com/wp-content/uploads/2017/12/01-1.jpg)

If I have 2 grams of gold valued at $100, and I need to pay $60 (so 60% of their volume) to move them from one end of my desk to the other, I would never move this gold. The defense against this argument usually goes something like: "_Transferring a kilogram of gold from Brazil to Germany is also expensive_" which while true, doesn't account for the fact that in those cases the distance is proportional to the price paid for moving the gold.

With BTC, the fee is identical whether I'm sending my "gold" across the globe or across a room. This makes any and all store transactions unfeasible and not just because of the fees but also the time it takes for the transaction to get confirmed. No store, regardless of how much more expensive its goods and services are when compared to the tx fees, could work like this.

This brings us to the second argument against Bitcoin as a store of value.

## 2. To keep possession of your gold, you don't pay rent to gravity

Bitcoin as a system depends [on miners][powpos]. Miners are computers which run [full nodes][nodes] and process the transactions submitted into the system. The miners get [block rewards][bw] for their work and those are currently at 12.5 BTC per block. A block is mined approximately every 10 minutes. This means 12.5 BTC are created every 10 minutes (more about this process [here][bc]).

[![Illustration from https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png)](https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/)

Along with the block reward, miners also get the fees attached to transactions in a given block. So if a block [contains 1000 transactions][blockex] and each of those costs $60, the miner who mined it gets a reward of $60000 + 12.5 * $16000 (current price of BTC) or a total of around $260,000.

However, every 4 years there's an event called "the halving" during which the block reward is halved. This is built into the Bitcoin protocol itself. Already in 2048 (almost a full 100 years before the ["last"][finite] bitcoin is mined) the block reward will be only 0.025BTC and in 2052 it will be only 0.0125 BTC. Even if BTC cost $1,000,000 by then, a reward of 0.0125 is only $12500 - less than today's cost of one full bitcoin.

If no one is moving their bitcoin because everyone is [encouraged to hoard][finite] because of the potential to appreciate, there are no transactions in the system. If there are no transactions, there are no fees with which to reward miners when the block reward becomes this insignificant. If the miners, who will by 2048 have facilities in the range of billions (those costs are close to that even today), are promised a reward of only $25000 every 10 minutes or so, that's not even close to being worth it. Miners will leave the system and move to other cryptocurrencies which are likely to pay the investments off sooner. Without miners there's no one to process transactions, so the "gold" becomes worthless because there's no way to "move" it. Additionally, with fewer miners the [centralization problem][isps] becomes an even bigger one. At this point, Bitcoin enters a death spiral.

![Death spiral](https://bitfalls.com/wp-content/uploads/2017/12/02.jpg)

The situation is thereby equivalent to paying rent to gravity in order to keep your gold in place. If you stop paying (in BTC it's either you paying or the miners with their enormous operational costs), your gold evaporates. To keep BTC around as store of value, miners need to **mine on empty**. This is why BTC will never be digital gold unless they accept one of the following solutions:

1. Gradually implement block size increases, increasing throughput. A common argument against that is that computers running [full nodes][nodes] would be too expensive for the developing world, making the network too centralized. Given that 60% of all Bitcoin traffic goes through only three major ISPS (more [here][isps]) and that current transaction fees already exceed a week's worth of wages in that developing world, I consider this argument moot. The block increase approach is the approach that [Bitcoin Cash][cash] took.
2. Move to [PoS][powpos] like Ethereum will. PoS does not require mining and removes a huge expense from the entire equation. This is not likely with BTC because of big industrial miners and companies in whose best interest it is to keep the Bitcoin network slow and unusable. These actors are too big to fail, and they simply won't allow it - to them it's existential.
3. Changing the Bitcoin software to ignore the theoretical 21 million coin limit, or to ignore the block reward halving. [I believe][finite] this to be the most likely outcome because those in charge of producing new bitcoins (the industrial miners) and the companies whose business depends on the network staying slow and expensive to use have it in their best interest to keep the status quo indefinitely.

![Corruption](https://bitfalls.com/wp-content/uploads/2017/12/03-2.png)

If you're thinking "_But 2048 is so far away, a lot of changes will come before then_", just remember that Bitcoin is already 10 years old and the political block-size war has been going on for three years now. The technology isn't progressing even close to the speed we need it to progress if we want to have practical solutions by the time 2048 rolls around, and the problems will become much more obvious long before then.

## Conclusion

Bitcoin maximalists often give two "counterarguments" to these claims:

1. "The Lightning Network (a Bitcoin upgrade) will allow for instant and almost free transactions in the order of millions per second". This argument will be disassembled in an upcoming post.
2. "Use something else to transact, like Litecoin, and use BTC as a Store of Value". This is not an argument. It not only fails to solve a problem, but also acknowledges the brokenness of the system we're discussing. If the answer to "system A is broken" is "then use system B", this does not justify system A's existence, unless it is fixable. Such an argument effectively acknowledges that system A can no longer be used for its originally intended purpose.

If we combine the aforementioned issues with the facts that one cannot code on Bitcoin like one can with [Ethereum][eth] so it doesn't have _utility_, and we take into account that it's [horribly centralized from an infrastructure perspective][isps] and [very vulnerable][unstop], being skeptical towards the whole protocol is nothing short of a healthy attitude.

![Skeptic](https://bitfalls.com/wp-content/uploads/2017/12/04.jpg)

But if it's so unusable, where is it getting its value? How can it cost $16000 per BTC? We covered this in the [Tether article][tether]. Besides - what do you think happens when you buy BTC on a platform like Coinbase? Do you really think it's BTC you bought, or is it just numbers in their database that get changed? How can you really be sure there's bitcoin behind the numbers unless you withdraw into [your own wallet][wallet]? Do you think they'd be transacting in the miniscule amounts of everyday customers with the fees in the range of $30-60?

There's a very clear definition of a ponzi or a pyramid scheme: if a product cannot succeed through the utility or sale of that product alone and instead depends on the number of new people entering the product's system, it's a pyramid or in the best case scenario, a bubble. Right now, it certainly looks like Bitcoin is heading in that direction. Will that change? As a bitcoin holder, I hope so. As a bitcoin skeptic, I've diversified a long, long time ago. We'll see what happens.

[unconf]: https://blockchain.info/unconfirmed-transactions
[max]: https://bitfalls.com/hr/glossary/#bitcoin-maximalist
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[isps]: https://bitfalls.com/hr/2017/11/29/new-threat-bitcoin-internet-service-providers/
[bchalt]: https://www.ccn.com/xapo-president-biggest-bitcoin-companies-move-bitcoin-cash-ethereum/
[steam]: https://www.theverge.com/2017/12/6/16743220/valve-steam-bitcoin-game-store-payment-method-crypto-volatility
[tether]: https://bitfalls.com/hr/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[fees]: https://bitcoinfees.info/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[powpos]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[bw]: https://bitfalls.com/hr/glossary/#block-reward
[block]: https://bitfalls.com/hr/glossary/#block
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[cash]: https://bitfalls.com/hr/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[unstop]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/