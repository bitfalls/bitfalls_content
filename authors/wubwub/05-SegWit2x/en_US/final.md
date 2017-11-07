Segwit? Segwit2x? Fork? NYA? You may have come across these terms in the past few months or weeks, but still don't understand what's happening? We'll explain in this post.

_If you're new to the cryptocurrency space, we recommend you read our newbie-friendly [intro to blockchain][blockchain] to absorb the necessary terminology._

## The Problem

Every blockchain has the same weakness - scalability. When a blockchain reaches the saturation point at which there's more pending transactions than the network can process, the speed of executing those transactions decreases. The transaction fee increases because [miners][powpos] will process transactions with higher fees first, so you can either have slow but cheap transactions, or fast but expensive ones.

The second problem is mining hardware optimization called [ASICBoost] which allows for a greater mining efficiency in the [electricity spent][powpos] versus [hashes per second][hashrate] produced. The Chinese company Bitmain - a producer of top of the line mining hardware - had ASICBoost built into their devices ([ASIC](https://bitfalls.com/glossary/#asic)s) giving their mining rigs a [+30% edge][ABoostGregMax] over the rest of the market's available hardware.

In finding the solutions to both the ASICBoost problem and the scalability issue, we have two opposing camps:

1. Core developers (developers working on the Bitcoin protocol)
2. Chinese miners

### Solution 1 (Core developers)

**Core devs** prefer the [Segregated Witness][SegWit] (SegWit from this point on) solution. It's more complex, but has more long term perks. It also lays the foundation for the _Lightning Network_ (LN) which will increase transaction throughput further by means of off-chain transactions. The LN technology is conceptually similar to [Ethereum's][eth] solution called [Raiden].

In a nutshell, the LN uses smart contracts and payment channels to make transactions happen off-chain. These fee-less transactions and microtransactions happen off the main chain and are committed to the main chain as a group once every few days. Only this main transaction has a fee then. This speeds things up significantly. The downside is the likely formation of bitbanks and centralized services through which these transactions will get processed before being sent to the main chain, which means the forming of a new banking sector in the crypto space. Likewise, LN takes the transaction fees away from miners, who had come to rely on them for rewards in the ever-decreasing [block reward](https://bitfalls.com/glossary/#block-reward) space of Bitcoin mining. When we consider [Bitcoin's "finiteness"][finite], that does not bode well.

For advanced readers, [this video][LightningNetwork] might explain things a bit more succinctly.

#### What is SegWit?

Like we explained in a previous post on [how to read Bitcoin transaction data][blockex], a Bitcoin transaction contains information such as the transaction size, input and output addresses, amounts, fees, and more. The most important part of this is the fact that each transaction has to be signed with a [private key][privatekey]. This signature takes up most of the space in a transaction, but without it we have no idea if the transaction is valid.

![Signature size](https://bitfalls.com/wp-content/uploads/2017/11/03.png)

By _segregating_ this _witness_ data out of the transaction, the core developers effectively halved the transaction size. The nodes that want to make sure the transaction is valid need to request this data separately by having software which supports the SegWit approach installed, like Bitcoin Core. This also means that the whole system is now trust based, until manually checked for truth.

### Solution 2 (miners)

Chinese miners with Jihan Wu at the forefront wanted to increase block size from 1mb to 8mb. This is not a long term solution because as Bitcoin gains more and more mainstream adoption, the same capacity problem would arise in the near future. An additional reason why the miners complained against the SegWit solution was the fact that the SegWit upgrade disabled ASICBoost, which makes them lose quite a big edge.

Furthermore, if blocks increase in size the people running nodes voluntarily would have to upgrade their storage and possibly internet connections to accommodate for the new throughput. Initial node synchronization would also take much longer (that's the process of downloading and validating the entire blockchain after installing the Bitcoin software of choice). 

![Bitcoin nodes](https://bitfalls.com/wp-content/uploads/2017/11/04.png)

It would become a little more expensive to run nodes, and nodes are just validators - they don't get anything for their participation in the network. It's possible that this would cause a bit of a centralization in the Bitcoin space due to only big data centers and corporations being able to afford to run nodes. This can potentially lead to a "corporate hostage" situation, much like with the Lightning Network above. Those who control the nodes control the Bitcoin network, and thus it's important that the ability to run nodes remain accessible to all.

Like we said in the [post about Bitcoin's false finality][finite], if node centralization occurs, those who control the majority can change the 21 million limit, reject valid transactions, change protocol rules, etc. This is very dangerous not only for Bitcoin but the the crypto ecosystem at large.

_Because the Bitcoin protocol is based on trustlessness, it is extremely important that the ability to verify transactions remains with the people._

### Solution 3: Segwit2x (compromise):

Activate SegWit first, the increase block size. This plan is called "Segwit2x".

Seems like a good compromise, no?

Despite the above reasons for each solution being suboptimal, it's more worrying to see who's actually behind Segwit2x.

#### NYA and SegWit2x

The [NYA (New York Agreement)][NYA] is an agreement among some of the biggest players in the Bitcoin space - companies and miners alike. The plan was to activate SegWit first (this already happened), and to double block size 90 days later. These two improvements would increase the theoretical capacity limit to around 8MB worth of transactions.

The development of SegWit2x is being spearheaded by Jeff Garzik, one of the original authors of the Bitcoin blockchain software. This agreement was not attended by Bitcoin Core developers - in part out of principle because closed door deals aren't in the spirit of Bitcoin, in part because most of them weren't invited.

![Behind closed doors](https://bitfalls.com/wp-content/uploads/2017/11/05.jpg)

Of the 56 initial companies from the NYA, 10 dropped out while 8 of them moved to Bitcoin Cash. This leaves us with 38 (at the time of writing) which still support the SegWit2x upgrade. You can keep an eye on the list of supporters [here][segwitstatus].

#### UAHF and Bitcoin Cash

After the initial compromise agreement, the aforementioned Bitmain mining hardware manufacturer backed out and initiated a [User Activated Hard Fork (UAHF)][UAHF] on August 1st, thus creating Bitcoin Cash. Bitcoin Cash has replay protection (protection from a dangerous attack on Bitcoin users we described in [this post][Bitcoin Gold]) and 8mb blocks.

The images below show some of the key proponents of SegWit2x (Jihan Wu and Roger Ver) promoting Bitcoin Cash. Why they would still be concerned about SegWit2x if they got what they wanted in the form of Bitcoin Cash is [anyone's guess][whycare].

![01](https://bitfalls.com/wp-content/uploads/2017/11/01-1.png)

![02](https://bitfalls.com/wp-content/uploads/2017/11/02.png)

## The Future

Neither the miners nor the Core developers are crucial for the Bitcoin ecosystem - it's the nodes. The beauty of Bitcoin is in the fact that it's a decentralized, democratic protocol in which anyone running a node at home can vote by applying some strict software rules. If miners activate SegWit2x and start mining bigger blocks, the nodes will not accept those blocks because they aren't valid according to Bitcoin rules. The miners will automatically fork into another chain, whereas the miners who mine under the original rules will stay on the legacy chain.

On the other hand, if nodes change their software in a way that lets them accept bigger blocks, then that chain becomes the main chain and the one with the smaller blocks dies off. It's all in the hands of the users. Unfortunately, the misinformation lobby spearheaded by those who have the most to gain with these political battles is already very strong, and objective information is very hard to find.

The current Bitcoin situation with too expensive transactions is slowly improving and SegWit transactions are being used [more and more][SegWitTx]. The fees are slowly dropping but they're still worryingly high. Despite these problems, the coming fork should not be taken lightly.

The main Bitcoin chain recently forked twice - since August 1st we have Bitcoin Cash, and since October 23rd, we've had [Bitcoin Gold]. If a new fork in November occurs and we get Bitcoin2x, we'll have four "main" Bitcoins, not counting all the previous forks like Litecoin, Dash, ZCash, Bitcoin Unlimited, etc.

This will cause chaos in the exchanges and among crypto newbies. It also poses a risk of significant losses due to people accidentally sending funds to a Bitcoin2x address from a Bitcoin address, or vice versa, or another incompatible combo.

The community's consensus is that a hard fork should be planned long in advance, up to two years depending on complexity, especially considering we're dealing with a market cap value of over 150 billion USD.

Take [Ethereum][eth] for example - it recently had its hard fork for the Byzantium upgrade (more about that [in this post][ethroadmap]), but this all went smoothly since the upgrade had been planned from day one (in 2014). In spite of the discussions and debates about Bitcoin scaling which had been happening for two years prior to NYA, SegWit2x was given only 3 months from the moment the agreement had been reached.

## Central Banks Attacking Bitcoin from the Inside

There's a [post on Reddit][redditpost] which lays out some evidence that the enemies of cryptocurrencies (the Digital Currency Group, MasterCard, and the world's most prominent bankers) are in fact taking over Bitcoin from the inside by means of this SegWit2x scandal. 

![The ruling class laughing](https://bitfalls.com/wp-content/uploads/2017/11/06.jpg)

We highly recommend you give it a read - you'll no doubt be left wondering how much we can trust the parties behind the upgrades, and who those responsible are actually putting in place of the current developers. One this is certain - Bitcoin is under attack from [multiple sides][Bitcoin Gold].

## What to Expect from Bitcoin's Price During SegWit2x?

_Note: This is not investment advice. It is merely the author's subjective opinion._

It's safe to assume the price will move similarly to how it did with previous forks.

![A sharp drop in price after a meteoric rise](https://bitfalls.com/wp-content/uploads/2017/11/07.png)

Shortly before the fork, the price will spike due to [FOMO] and the desire to get the "second coin for free", while [altcoins] will drop in value (this has been happening for a few weeks already).

Immediately after the fork, one coin will be sold to increase holdings in the other, or for promising altcoins. The winning Bitcoin might rise in value just like Bitcoin Cash did.

Here's what you can do:

1. Sell Bitcoin now that it's high and wait for things to calm down.
2. Try to day-trade and use the price swings (not recommended - high risk high reward scenario)
3. [HODL], a safe solution if you believe in the technology or just want to keep both coins.

It's important to note that if you're holding your coin on an exchange, it's up to them to give you the new coins. They can, but they don't have to. It's up to them. That's why it's safest to store your cryptocurrency key privately, either on a Ledger wallet, or a [piece of paper][paper] - and this advice applies to both during the fork and during stable times. Keeping money in an exchange is a bad idea.

If for some reason you're not feeling overly confident in your ability to safeguard your coins, feel free to [contact us about that][manageportfolio].


[paper]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[hashrate]: https://bitfalls.com/glossary/#hash-rate
[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[SegWit]: https://segwit.org
[privatekey]: https://bitfalls.com/glossary/#private-key
[ASICBoost]: https://www.asicboost.com
[ABOOSTGregMax]: https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-April/013996.html
[hash]: https://bitfalls.com/glossary/#hash
[Raiden]: https://bitfalls.com/2017/10/02/ethereums-development-roadmap-metropolis/#raiden-network
[LightningNetwork]: https://www.youtube.com/watch?v=MpfvhiqFw7A
[UAHF]: https://cointelegraph.com/explained/uasf-vs-uahf-explained
[NYA]: https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77
[segwitstatus]: http://segwit.party/nya/
[fork]: https://bitfalls.com/glossary/#fork
[Ethereum]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[ethroadmap]: https://bitfalls.com/2017/10/02/ethereums-development-roadmap-metropolis/
[publickey]: https://bitfalls.com/glossary/#public-key
[Bitcoin Gold]: https://btcgpu.org
[redditpost]: https://www.reddit.com/r/btc/comments/743qb8/is_segwit2x_the_real_banker_takeover/
[dcg]: http://dcg.co
[dcgleaders]: http://dcg.co/who-we-are/
[LawrenceSummers]: https://en.wikipedia.org/wiki/Lawrence_Summers
[BitGo]: https://www.bitgo.com/solutions
[mastercard]: https://www.youtube.com/watch?v=Tu2mofrhw58](https://youtu.be/Tu2mofrhw58?t=170
[blockstream]: https://bitfalls.com/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/#segwit2x
[replayprotection]: https://bitfalls.com/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/#replay-attack
[SegWitTx]: http://segwit.party/charts/#
[FOMO]: https://bitfalls.com/glossary/#fomo
[altcoins]: https://bitfalls.com/glossary/#alt-coins
[HODL]: https://bitfalls.com/glossary/#hodl
[manageportfolio]: https://bitfalls.com/portfolio-management/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[whycare]: https://www.reddit.com/r/btc/comments/75u35x/bitcoin_cash_vs_b2x/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[blockex]: https://bitfalls.com/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[powpos]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/