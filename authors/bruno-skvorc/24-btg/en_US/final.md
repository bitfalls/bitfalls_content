The beauty of the [blockchain][bc] is in the fact that everyone can decide to split the blockchain off into their own version at any time if they disagree with the development philosophy of the main team.

This is what happened in August with Bitcoin Cash. The dev team behind it wanted to increase [block size][blockex] so that more transactions could fit and get processed. The "main" Bitcoin Core team, on the other hand, wanted to move a big chunk of data from the transactions into a separate chain and thus make more of them fit into existing [blocks][block] that way.

When such a fork happens, we call the resulting new fork a _contentious fork_. More about forking itself in an upcoming post.

## Segwit2x and BTG

![A Fork in the Road](https://bitfalls.com/wp-content/uploads/2017/10/01-3.jpg)

Soon, two more forks are happening. Let's explain them real quick.

### Segwit2x

In November 2017. (around the 18th), there will probably be a Segwit2x fork. This fork has been dragging on since the Bitcoin Cash days, and is all about political strife and disagreement. The Cash fork happened because one team was against the Segwit upgrade (the removal of a big part of transaction data into a separate chain) and wanted to increase block size. This group made Bitcoin Cash. Bitcoin Core implemented Segwit, but the percentage of their usage is disappointingly low even after all this time - both with users and software - which is why Bitcoin transactions are still so slow and expensive. A simple $1 transaction can cost $5 and last for 12 hours, which is just borderline unusable.

From a technical standpoint in regards to Segwit2x, one group *again* wants to increase block size while the other is very much against this move. If the blocks stay small, the devs need to work on solutions that move transactions completely out of the main chain and into sidechains which have their own context in which to execute transactions. For example, a simple shop doesn't need to confirm each transaction on the main chain - it can perform them all day in a side chain, and then just validate the whole set as one transaction. The system is still safe, but faster and cheaper.

![Old cash register](https://bitfalls.com/wp-content/uploads/2017/10/02-3.jpg)

However, moving transactions out of the main chain also moves the transaction fees, and miners are then no longer rewarded as much for processing transactions. Interestingly, a company called Blockstream specializes in sidechain implementations. Something that'll get more interesting a few paragraphs down.

On the other hand, those who want bigger blocks are mainly miners because, predictably, they're finding it most beneficial. Concretely, the bigger the block, the more transactions can fit, the more the miner can earn on transactions fees, the more transactions get processed, the less they cost. Ideally, the best system would have a combination of both these approaches, but both sides devolved into extremist parties completely incapable of compromise and collaboration.

Now, objectively, Bitcoin is technologically retarded when compared to almost any other blockchain. The only thing keeping it at the top is its brand recognition coupled with the first mover advantage. It was the first and thus remains biggest, for the time being. [Ethereum][eth] is already processing more transactions than Bitcoin is, and it's used not just as a monetary instrument but also for programming. These are the downsides that are forcing the devs to upgrade Bitcoin, and this is where the disagreements come from - they can't come up with a solution that benefits everyone.

In addition to everything above, the Blockstream company organized not only a censorship of the [r/bitcoin](https://reddit.com/r/bitcoin) subreddit and thereby forced the creation of [r/btc](https://reddit.com/r/btc), but also pushed some of the developers out of the core team responsible for Bitcoin. The ones who are left are people with questionable logic (one of the leading people, for example, believes that the sun revolves around the Earth, among other [amazing opinions](https://www.reddit.com/r/Buttcoin/comments/4936kw/lukejr_is_a_seriously_a_super_crazy_person_quotes/)), and most are actually paid by Blockstream. While commercial support for an open source project sounds amazing and altruistic, all it takes is a little bit [of research][research1] to [see][research2] that Blockstream is commanded by the Bilderberg group: a powerful group of elites who control the world's financial systems via control of banks, and see cryptocurrency as the mortal and existential enemy, thus sabotaging it from the inside with bad software solutions.

![The silhouette of a business-clad man dancing in front of a Euro sign](https://bitfalls.com/wp-content/uploads/2017/10/03-2.jpg)

Just as it happened with Bitcoin Cash, the new B2X fork will also give out "free" Bitcoin in the same amount you now own. So if you now have 1 BTC, on November 18th you'll have 1 BTC and 1 B2X. See the "How to get the tokens" section for info on safely obtaining them.

### Bitcoin Gold

Bitcoin Gold appeared as an idea some time [in July][btgann]. Jack, the author, presented BTG as the "savior" of Bitcoin by making it ASIC-resistant and thus freeing it from the grasp of giants like Bitmain - a company producing powerful [ASIC][asic] miners - devices for highly efficient [mining]. Bitmain has a huge monopoly over these devices and thus the processing power that governs the Bitcoin blockchain. Mining in general is heavily centralized in China at around 80% of the hashing power being there, with Bitmain themselves holding around 40%.

His goal is to make Bitcoin mineable by regular GPUs again instead of ASICs, giving control back to the non-corporate miners. While this does sound okay, there are several oddities about BTG and the team:

1. Until the very day they wanted to launch their project, the team had done *nothing* technologically, as evident [here][trello].
2. Their [code][btggh] is borked and won't even build and run.
3. The project's owner also owns a company which sells ASICs and mining gear, probably specialized for the exact methods BTG was going to use.
4. They say BTG will be ASIC resistant, but the resistance procedure is not described in any whitepaper, and is almost completely absent from the code.
5. The fork already happened. Some BTG was pre-mined before the blockchain was even publicly released. They lied about this on their website.
6. The same people who own the BTGGPU domain own the following [fishy domains][domains].
7. As [this redditor][reddit] discovered, BTG was pre-mined, kept secret, offered as na ICO (initial coin offering, a pre-sale at 10 BTG per 1 BTC) and kept secret again after the ICO failed, before finally being repackaged as BTG and offered to unsuspecting masses.

Worrying.

![Zabrinuta viktorijanska žena, ilustracija](https://bitfalls.com/wp-content/uploads/2017/10/04-4.png)

All in all, BTG sounds like a well planned scam which would set up a good ground for replay attacks designed to steal from unsuspecting and/or greedy investors. More about replay attacks in the sections below, but our recommendation is to steer clear of BTG or wait for at least 3-4 weeks before starting to trade it.

Surprisingly, this seems to be the one thing *everyone* in the crypto world is agreeing on - and you know that's rare.

## The Fork Effect

Sadly, most people are very greedy and when they just hear the word "fork" they think "free money". Along with [certain manipulations][fraud], this causes enormous BTC buying spikes, driving the value up artificially, and a huge drop afterwards, as people sell off their "free" gains. But if everyone's selling... who's buying?

If you're one of those hoping to sell BTG off successfully, be careful - you don't want to be become a [bagholder].

You won't find profits any faster than by just [buying a promising currency][buycc] and waiting it out. Forks are often traps and tricks meant to make you vulnerable to replay attacks, and can seriously harm you.

## Replay Attack

When a fork happens, the part of software which signs transactions (more about that [here][bc]) remains valid on both chains, unless the splitting chain changes it. This means that any transaction which occurred on chain A can be replayed on chain B without the user's presence because it's already generated and signed. This copying of transactions from chain A to chain B with the intent of replaying it is called a replay attack.

![Dvije strelice koje se vrte u krug, jedna pokazuje prema kraju druge](https://bitfalls.com/wp-content/uploads/2017/10/05-4.png)

If someone copies your house keys, the only way to be completely safe from intruders is to change the lock, because you have no idea into how many hands it had already been distributed. Hunting all the copies down would simply not be efficient or possible.

Bitcoin Cash almost immediately implemented replay protection and secured the network. Many other forks are, however, made with the express intent of making gullible people vulnerable to such attacks. Big transactions are collected with software like the [Blockexplorer][blockex], and simply copied over onto the original chain.

Bitcoin Core (BTC's original chain) could have implemented replay protection ages ago and made all future forks powerless, but they chose not to do this for some reason. It should be noted that it is, admittedly, harder for an original chain to implement it because the amount of software that needs updating is in such cases enormous.

### How can BTG replay attack me?

Please note that the BTG team **claim that they have replay protection when they [obviously do not][btgrp]**.

Here's how you can get attacked:

- step 1: a naïve investor buys 2 BTC to score 2 free BTG on fork time.
- step 2: the person behind the BTG project (let's call him Jack) impersonates a buyer at an exchange or other app, and buys BTG for $500 or $1500, doesn't matter how much
- step 3: Jack takes a copy of the transaction he just performed with the naïve investor
- step 4: Jack sends the transaction in the same form onto the main chain
- step 5: if our investor still has 2 BTC in his address, they are stolen. Jack made 2 BTC minus the price he paid for BTG.

Now multiply that with the number of people you saw all over the web asking about Bitcoin Gold and getting free BTG in the past few weeks.

![A worried robot toy](https://bitfalls.com/wp-content/uploads/2017/10/06.jpg)

Seeing as BTG has no RP, how can one secure their assets?

- option 1: send BTC to another address you own first, then use BTG.
- option 2: wait until you see the final purpose of BTG - to be revealed within a few weeks. Don't let greed pull you into this mess.

## How to Get Forked Tokens

The **only 100% safe way** to get forked tokens is to have the private key of your wallet. If you have it, you're good. If your BTC is on an exchange, it's up to the exchange to give you the forked coins or keep them. They have every right to keep them.

We repeat: the **only** safe way is to have your own wallet's private keys with you - not in an app, not online, but with you offline, or in cold storage, or on a Ledger or similar.

If you're not sure how wallets work, see [here][wallet]. To secure your tokens, both original and forked, use one of [these approaches][paranoia] or [buy][shop] the impenetrable [Ledger Nano S][ledger]. Or just generate your own address [like so][startbtc].

After the fork, wait a while (at least for a week) until you see whether or not the replay attacks have been resolved. Then, and only then, take control of your forked token. By then you'll know which exchanges support them and you'll easily be able to send them there and trade.

Alternatively, if you're really not confident in pulling it off on your own, get in touch about our [portfolio management services][folio]. We'll take a cut, yeah, but we'll also guarantee and insure your amount and we'll do it like pros.

## Conclusion

TAKE IT SLOW!

![A "slow" traffic sign, shaped like a child running into a street to scare drivers](https://bitfalls.com/wp-content/uploads/2017/10/07.jpg)

Be very skeptical about every fork and look into as many circumstances that lead to its creation as you can. Talk to people, don't be ashamed to ask questions, and don't fall for sensationalist titles of amateur publications.

If you're not able to understand what it's about or some terms are confusing to you, ask us - we're on Twitter, Facebook, email, even in the comments here. We're here to help and prevent losses.

Don't fall for marketing campaigns, ignore your optimistic relatives, and approach everything in the crypto world with a healthy dose of skepticism - the industry is still too young for fairness.

Trade carefully!

[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[research1]: https://www.reddit.com/r/btc/comments/47zfzt/blockstream_is_now_controlled_by_the_bilderberg/
[research2]: https://www.reddit.com/r/btc/comments/4v26v9/is_there_a_source_that_explains_the_whole/
[blockex]: https://bitfalls.com/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[block]: https://bitfalls.com/glossary/#block
[buycc]: https://bitfalls.com/how-to-buy-cryptocurrency/
[fraud]: https://bitfalls.com/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[bagholder]: https://bitfalls.com/glossary/#bagholder
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[paranoia]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[ledger]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[shop]: https://bitfalls.com/shop
[folio]: https://bitfalls.com/portfolio-management/
[btgann]: https://bitcointalk.org/index.php?topic=2046790.0
[asic]: https://bitfalls.com/glossary/#asic
[mining]: https://bitfalls.com/2017/10/12/mining-investing-cryptocurrency-better/
[startbtc]: https://bitfalls.com/2017/09/01/send-receive-bitcoin/
[btgrp]: https://github.com/BTCGPU/BTCGPU/issues/51
[trello]: https://imgur.com/a/tZja4
[btggh]: https://github.com/BTCGPU/BTCGPU/commit/e7bfc903d97bb160e13d2674506591aa7878d726
[domains]: [https://i.imgur.com/HG31eie.png](http://viewdns.info/reversewhois/?q=xiangliao%40gmail.com)
[reddit]: https://www.reddit.com/r/CryptoCurrency/comments/757jf4/here_is_why_bitcoingold_is_shady_and_a_scam_you/