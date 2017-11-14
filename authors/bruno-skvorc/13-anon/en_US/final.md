An argument financial institutions, politicians, and regulators often cite against wide adoption of [cryptocurrency][cc] is the fact that it's anonymous and thus ripe for use by criminals and terrorists.

## Let's ignore...

Let's ignore the fact that cash will never be completely removable from society. A government can maybe criminalize all cash transactions, or [remove 85% of the monetary value of cash from an entire country overnight][india], but this turns all citizens into criminals and we're talking about a runaway dictatorship. Changing the way money works will only punish those with good intentions, and be fully bypassed by criminals who will easily switch to another form of payment.

Let's also ignore the fact that even if cash is completely removed from circulation, the criminals the government is supposedly afraid of can trade in gold, silver, oil, diamonds, even [Tide detergent][tide].

![Secured jugs of Tide](https://bitfalls.com/wp-content/uploads/2017/09/01-3.jpg)

Let's also turn a blind eye to the fact that, in most countries, the black market exists only because the "white" market failed the people. For example, there's a [black market for food](http://www.npr.org/sections/thesalt/2017/01/09/508986586/as-venezuelan-go-hungry-the-military-is-trafficking-in-food) in Venezela because they simply *don't have food*. During the Russian depression in the 1980s, there was a [black market for US Dollars][dollarus] because Rubles were considered worthless by many establishments. It's worth noting that when a society's black market is based on opiates, porn, or other recreational types of contraband, that's generally a pointer of how good things are in that society - it means all the basic needs of its people have been fulfilled. Such societies are in fact very rare.

Finally, let's also ignore the fact that we're asking the very same entity which governs our money supply to regulate itself, and that we're giving it complete freedom to decide the value of said money. When such freedom exists, is it even surprising to find out that it's actually [the governments who are funding terrorism directly][terror]? But like we said above, let's ignore this.

Instead, let's focus on what they're allegedly afraid of: anonymity.

## Bitcoin and Anonymity 

![The icon of anonymity - a Guy Fawkes mask](https://bitfalls.com/wp-content/uploads/2017/09/02-2.jpg)

First, it's important to know the difference between privacy and anonymity.

When you buy or sell something and what you've bought or sold or for how much isn't logged anywhere, that's privacy. When you buy or sell something and no one logs *who* did the buying or selling, that's anonymous. 

A cash, goods, or services (or any mix thereof) exchange is both private and anonymous, especially if there's no receipt and the parties don't know each other. A credit card purchase is neither, because it's clearly logged who bought what for how much and when.

Bitcoin is _partially anonymous_ and _not private at all_ because of the way the [blockchain][bc] works.

Why _partially_? Because most people don't enter the crypto world through anonymous means. Because of the relatively high complexity of getting your first bit of cryptocurrency (generating a [wallet], getting BTC from someone, storing BTC, learning [how to use it][startbtc]...), many first timers buy their first batch through platforms like [Coinbase][coinbase], [Litebit][litebit], or [Cex][cex] which make this process incomparably smoother.

However, on all of these exchanges, buying any non-trivial amount requires you to pass KYC and AML measures (know your customer and anti-money-laundering) by submitting personal ID - sometimes even a photo of yourself holding a government issued ID or even the bank card you intend to use. Once you send this information along, your bitcoin address is as anonymous for you as a traditional bank account: not at all. Hence, it's realistic to conclude that anyone interested in using bitcoin in a legitimate way would have nothing to hide and thus use it in such an open way.

![Biometric logging caricature](https://bitfalls.com/wp-content/uploads/2017/09/03-2.jpg)

If, however, a user should enter the crypto space through other means which maintain anonymity (e.g. mining, cash purchase, being paid in BTC for services), anonymity is again fragile at best. Here's how one can lose it.

## Losing Anonymity

### Carelessness

Since the state of the entire [blockchain][bc] is public, making one slip-up and publicly exposing ownership of an address (looking at your balance on a public computer, signing a forum post with a bitcoin address, buying from a bitcoin-enabled online shop...) is enough to permanently bind a person's real identity to the blockchain and their actions on it (see transaction graph below).

### IP Identification

When a bitcoin user generates and sends a transaction from their computer, their transaction is sent to all other bitcoin software (miners) who take part in the bitcoin protocol and need to confirm this transaction.

Because not all computers are next to each other and some are on the other side of the planet, the signal takes longer to reach those that are further away. Every miner that receives a transaction also logs the IP it came from. An IP address is a literal address in the "internet space" which defines where a computer is, so that others connecting to it can find it. Every internet connected device has its own IP address.

If an authority gets its hands on enough logs of IPs from different miners, they can compare this to the timestamps of when a signal reached a given machine and use this to extrapolate the geographical location of a transaction sender. Worst case scenario it can narrow down the search area to a block or a town, best case it'll lead them right to the doorstep of the person they're interested in. There's a neat research paper on this [here][bitip].

![How the internet works](https://bitfalls.com/wp-content/uploads/2017/09/04-1.jpg)

An IP address can be partially obscured by Tor, but even that [isn't very safe][tor].

Naturally, if you're using exchanges which hold many hundreds of thousand of bitcoin addresses at any given moment and change them regularly, then IPs don't matter much. *Unless* these exchanges keep logs of IPs, past addresses, and transactions as well, as they're required by law, in which case this information can again be subpoenaed and analyzed.

### Transaction Graph

The most advanced method, the [transaction graph][tg], encompasses tracking the blockchain itself in great detail.

As a general rule of thumb, bitcoin users should use a new address with every transaction to increase privacy and to be safe - you never know who's got your private key once it's touched the internet. Hence, it's recommended that when sending amount X from address A to address B, the sender also have an address C generated to which they should send the leftover funds from address A.

The transaction graph takes this into account. If a transaction has more than one input address, then it is logical to assume that those addresses belong to the same person or group. If a transaction has multiple outgoing addresses, it is assumed that the address that has never appeared in the blockchain before is the leftover address - the one to which you send whatever was left on the first address after sending to the originally intended one. If we then take into account the human tendency to use whole numbers, it is reasonable to conclude that if a transaction contains a whole amount of BTC to one address and a fractional amount to another (i.e. 3 BTC vs 2.5379824792878972 BTC), the latter is probably the leftover while the former is the recipient. The same assumption can be verified if we convert the BTC to fiat, though this is a little more complex - it entails knowing what the target fiat currency was, and knowing the exchange rate on the exact date and time in question.

![Transaction graph example](https://bitfalls.com/wp-content/uploads/2017/09/05.png)

But all this merely maps the path of a given amount through the blockchain, it doesn't actually bind an identity to all this. To identify the transactors, we must remove the unknown from the equations we're interested in. This is done by replacing addresses in the graph with known entities.

For example, various online shops accept bitcoin only on one address, keeping it fixed across time. The same goes for various organizations accepting donations. Forum users will sometimes have their bitcoin address in their signature, while at the same time being blissfully unaware of all the private information they had left behind on those forums already. Some even have bitcoin addresses in email signatures. Mentioning you've bought a cute pair of Star Wars socks with bitcoin to someone may seem innocent enough, but if that someone knows that this pair of socks is sold by one shop only, and combines the purchase price of the socks with the estimated time of purchase and the shop's BTC address, they can easily find *your* address, forever identifying you in the blockchain. Further along in the future, if anyone ever needs to find something out they can use that as a starting point and unravel your transactional history.

By combining all three methods, the authorities have caught the owner of Silkroad - a notorious black market of drugs, weapons, and other contraband. The programmers among you can have some fun with transaction graphs on your own with tools like [these][sparkx].

## Conclusion

Bitcoin is not private, and is only partially anonymous. The most anonymous cryptocurrency right now is Monero, closely followed by Dash, ZCash, Verge, Vertcoin, and soon Ether.

Bitcoin transactions are easy to follow, but even if they weren't, trying to fight cryptocurrency at a government level is going to produce the same net effects as the war on drugs did. In other words, cryptocurrency would be driven underground where all the people who had been using them thus far would just continue using them, resulting in fraud, crime, heists and other dangerous scenarios, and - as with drugs - 0% tax collected.

The only *right* approach is:

- clearly define tax regulations and obligations of cryptocurrency users

and

- accept the fungibility of cryptocurrency. In other words, make it irrelevant where the money came from just like with cash, and treat every [Satoshi][finite] as its own, clean unit.

The only way to fight criminal use of cryptocurrency is full nation-wide decriminalization and acceptance as a currency. Any prohibition will only cause the technology to go underground where crime will flourish, at the same time negating completely any and all potential positive effects.

[terror]: http://www.balkaninsight.com/en/article/the-pentagon-s-2-2-billion-soviet-arms-pipeline-flooding-syria-09-12-2017
[tide]: http://nymag.com/news/features/tide-detergent-drugs-2013-1/
[india]: https://www.bloomberg.com/news/articles/2016-11-23/india-s-cash-canceling-experiment
[dollarus]: http://www.nytimes.com/1987/07/22/world/in-soviet-rubles-coupons-and-real-money.html?mcubz=0
[tor]: https://arxiv.org/abs/1410.6079
[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[startbtc]: https://bitfalls.com/2017/09/01/send-receive-bitcoin/
[litebit]: https://www.litebit.eu?referrer=111550
[coinbase]: https://www.coinbase.com/join/542b0423734ab06764000001
[cex]: https://cex.io/r/0/up108919585/0/
[bitip]: https://arxiv.org/pdf/1405.7418.pdf
[tg]: https://arxiv.org/abs/1502.01657
[sparkx]: https://github.com/ZuInnoTe/hadoopcryptoledger/wiki/Using-Spark-Scala-Graphx-to-analyze-the-Bitcoin-transaction-graph
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/