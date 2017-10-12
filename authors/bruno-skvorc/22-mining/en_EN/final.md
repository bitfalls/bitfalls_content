Mining. At first glance an amazing opportunity for getting rich by _legally manufacturing_ money in your own home. But is that really what it's like? We'll explain some common misconceptions in this post, and describe the payout rates on an example we tested as a funding option for Bitfalls.

It's important to note that this article only deals with [PoW] mining - so the type of mining described in this [intro to blockchain][bc] post.

## Type of Mining

There are three main types of mining:

- rig mining, which can be one of two types: pool mining, and solo mining
- cloud mining
- browser mining

We'll explain all of these a bit further down, but they all follow the same procedure:

- a computer (miner) downloads a bunch of information from the internet which claims who sent how much of a given [cryptocurrency][cc] to whom. These downloaded transactions need to be confirmed / validated.
- The miner builds a [block] of these transactions - an ordered list. The number of transactions in a block depends on the block's capacity, and on the size of the transactions. Transactions with multiple senders and multiple recipients take up more space than those with fewer senders/recipients, as explained in [this post][blockex].
- The miner combines all the transaction data (literally glues it together), some other arbitrary data, and a random nonce - a random value it tries to guess. This all gets [hashed][algo], and if this [hash] matches some rules as defined by the mining software (e.g. a specific number of zeroes at the front of it), it's considered valid. The block is thereby mined. The computer literally does the following: "Try summing all this and the number 1. No? Ok, try summing all this and the number 2. No? Ok, try..." until it guesses the number (the nonce). 
- The more powerful the computer, the more guesses per second it can do.
- After guessing right and _mining a block_, the computer that did it [gets a reward][bw] from the blockchain. In bitcoin's world, that reward is currently 12.5 BTC per block. In Monero's world, that's 6.18 XMR at this moment.

The computing power of a computer is measured in hashes per second (H/s). Depending on the algorithm being used, using graphics cards is often better than using CPUs (central processing units), so you'll often see mining rigs (machines) composed almost entirely of a power supply and graphics cards.

The stronger a computer is, the more chances it has to guess correctly. This is where the first misconception comes from.

## Misconception 1: patience pays

![Sand timer](https://bitfalls.com/wp-content/uploads/2017/10/01.jpg)

People often enter the mining world thinking "So what - even if my computer isn't the strongest of them all, sooner or later I'll guess a block and get the reward. Even if it's in 5 years and I get 12.5BTC then, at current prices that's $65000, so it was worth it!"

This is a misconception not only because the reward won't be nearly as high as it is today, but also because many don't understand that mining is **competitive sport**.

When a block is being mined, miners are actually racing each other to who will be the first to guess correctly. Only the first one gets the reward - the second or third miner to reach the same solution gets nothing (except in the Ethereum blockchain where the second miner sometimes also gets a so called aunt/uncle reward of 50% less Ether). Hence, competing against very powerful machines is mostly pointless, especially in popular cryptocurrencies like Bitcoin.

This problem can be circumvented by using _pool mining_ in which the guess attempts of the user's machine are sent to a pool of guesses also populated by the guesses of all other participants. This pool is then the "solo" miner, and once it gets a reward it distributes it proportionately to all participants, depending on how many hashes they sent in.

The pool owner generally takes a fee - 1-2% - which diminishes the reward slightly, but on average increases it purely because the power of a joint community almost always outweighs the power of an individual.

## Misconception 2: long term, my return on investment will be positive

"I don't want to join a pool, I want all the profit to myself", some will think as they head into a computer parts store to get a cart of graphics cards with the intention of assembling a powerful rig.

![Mining rig](https://bitfalls.com/wp-content/uploads/2017/10/02.jpg)

#### Example:

One of our readers heard from his friends that he can make money mining Ether. He had been thinking of investing 9000 euro to buy 4 powerful mining machines. They told him the earning potential is 330 euro per month per machine, or 280 when they subtract 50 for electricity costs. Seems simple, right? 4 * 280 per month (around 4.8 Eth) would return that investment in 9 months, and that's if Ether stays at the same price level. If we conservatively estimate that Ether's price will grow only 50% in one year, and our reader can afford to stockpile it without having to spend it immediately, he can earn 13300 after year one - a solid profit.

There are several problems with this:

- Ethereum is moving to a [PoS] system soon, so powerful mining machines won't make much sense
- The [block reward][bw] is getting smaller and smaller in Ethereum. It's 5 right now, but will be 3 very soon, and even less soon after that. A 40% reduction is anything but trivial.
- The mining [difficulty][bd] is increasing at the same time as the block reward is decreasing, with the intention to scare off new miners as the system prepares for PoS.
- Electricity costs money and can get more expensive at any moment, moving the profit margin into the red. How often do you see electricity becoming cheaper? Now think how often you've seen it become more expensive. Solar or wind power are an option, of course, but the amount of power required surpasses reasonable numbers if all the power is going to be used for is mining. Not to mention the upkeep costs of such a system, and the renewable energy taxes the oil industry is lobbying for.
- hardware can burn out. Graphics cards that are constantly at 120% of their computing power have a far shorter lifespan than when used in a traditional way. The warranty is usually 2 years. If the producer thinks the card won't outlast 2 years, how long do you think it'll last if pushed to its limit for 2 years? There's also the power supply and other components that can burn out.

Now let's look at the scenario of investing those 9000 euro directly into Ether. After 1 year, the price hike of 50% means our reader now has 13500. The same profit in the same time span, no stress, machines, maintenance, taxes, etc. He can now invest it in something else, or lay back and enjoy the earnings.

"But", you might be thinking, "if Eth changes that much, we can always mine something else, right?". This is the third misconception.

## Misconception 3: there will always be something to mine

Depending on the algorithm being used by a cryptocurrency's PoW consensus, a given currency will be harder or easier to mine with specific gear. For example, some algorithms work better on CPUs, which makes the high powered graphics cards suboptimal for mining it. Others work extra well on AMD graphics cards as opposed to Nvidia GPUs, thus making a stack of powerful Nvidia GPUs less useful. Some are so incredibly hard to execute on consumer grade hardware that people have to buy [ASIC] devices - small computers designed with one algo, one currency, and one purpose in mind. That's the case with [AntMiner][am] hardware by the company Bitmain, the world's foremost mining equipment manufacturer.

![An old mine](https://bitfalls.com/wp-content/uploads/2017/10/03.jpg)

Whichever currency you choose for your mining efforts, remember to study its long term plans first, and check for potential changes in algorithm or difficulty when accounting for profitability.

## Profitability

We can easily conclude that solo mining isn't worth it. But if you've already got equipment or just really want to try your hand at mining, pool mining is a fine alternative. If you don't have a machine but would like to participate in this gold rush anyway, there's also **_cloud mining_**. With cloud mining, you rent a remote machine and pay for this in regular currency. From then on, it's the same as pool mining - the rented hardware joins a pool, mines, and kicks the profits back to you, minus the amount you spend for renting.

Finally, there's a new approach: browser mining. It's the method [PirateBay recently abused][tpb] and one we've also [tried our hand][money] at here at Bitfalls.com in order to avoid having to go down the ads route. Coinhive is in fact *also* pool mining, only you don't mine with your machine - your website's visitors do, little by little. With enough visitors, it can easily replace a powerful mining machine.

So which of these methods pays the most? Here are some numbers we can share.

Bitfalls.com currently has around 8000 visitors per day. With the CoinHive miner (the browser mining method) we've sent in around 152.5 million hashes in the first two weeks. This earned us 0.2 XMR or, at the price of $90 / XMR, some $1.8. This would make it $3.6 per month, which is obviously unsustainable - especially considering many people told us the website was crashing on mobile devices, and that their antivirus programs kept flagging it as malicious due to this mining script being there.

![Ukupno hasheva na coinhive](https://bitfalls.com/wp-content/uploads/2017/10/04-1.png)
  
For comparison's sake, we activated a single GTX1080 Strix graphics card and connected to the [nanopool] mining pool. In one week, that card made us 0.06 XMR. From a purely mathematical standpoint, a single graphics card is 6 times as profitable as a website with 8000 visitors per day - but only if the electricity is free. If we punch in the electricity costs which amount to around $15 per month, we're left with a profit of around $10 per month if XMR remains at $90.
  
![Ukupno hasheva nanopool](https://bitfalls.com/wp-content/uploads/2017/10/05-1.png)
    
As you can see, the profitability is questionable at best unless you're using specialized mining hardware (ASIC) or have free electricity. If you have both, then you're quite competitive.
  
The example above refers to Monero (XMR) - the only currency you can mine through the browser right now - but the payout is similar with other currencies.

## Conclusion

Mining is a stressful, demanding, and mostly unprofitable business unless you have some prerequisites like advanced hardware or free power - preferably both. It has many risks and few gains - our opinion is that it's much better to earn money by purely investing, which is less risky and at the same time helps new and revolutionary projects that need funding get that funding.

If you'd like to try mining anyway, [What To Mine][wtm] will be a priceless resource. Good luck!

P.S. If you're already mining or are experienced with it, we'd like to know more. Get in touch in the comments below or write us an [email][mail] - we're interested in profitability, expenses, optimization tricks, and more.

[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[block]: https://bitfalls.com/glossary/#block
[blockex]: https://bitfalls.com/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[hash]: https://bitfalls.com/glossary/#hash
[algo]: https://bitfalls.com/glossary/#sha-256
[bw]: https://bitfalls.com/glossary/#block-reward
[pos]: https://bitfalls.com/glossary/#pos
[pow]: https://bitfalls.com/glossary/#pow
[bd]: https://bitfalls.com/glossary/#difficulty
[mail]: mailto:contact@bitfalls.com
[wtm]: http://whattomine.com
[asic]: https://bitfalls.com/glossary/#asic
[am]: https://www.bitmain.com/
[tpb]: https://bitfalls.com/2017/09/17/thepiratebay-steals-cpu-mine-cryptocurrency/
[money]: https://bitfalls.com/money/
[nanopool]: https://xmr.nanopool.org