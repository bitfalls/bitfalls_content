Tether.to, the company that's had some [suspicious patterns of behavior][fraud] of late, [has announced][announced] that it's been hacked for 31 million USDT. Remember, Tether is a company which has central authority to issue USDT tokens. USDT tokens are allegedly issued in a 1:1 ratio with real USD deposits. This holds true if we observe the price graph over time, as fluctuations are truly minimal.

![Tether price over time](https://bitfalls.com/wp-content/uploads/2017/11/01-3.png)

What's interesting is that USDT were stolen, and not another cryptocurrency, which is odd given that Tethers are actually [worthless][tether1]. Tethers aren't in fact a [cryptocurrency][cc], they're merely a token on the [Omni] layer which isn't a [blockchain][bc] per-se - it's a software layer on top of the Bitcoin network, which adds new features to Bitcoin's underlying transactions.

The approach they took in "solving" this problem is odd. They decided to make a change to the [wallet] software - a hard fork - which renders all current versions of the software incompatible with the old ones. Specifically, the code of the wallet has been altered in such a way that a single address was blocked and blacklisted as a sender, but not as a recipient. This means the address can receive funds, but not send them out, effectively trapping the stolen USDT in place.

![Tetherova solucija](https://bitfalls.com/wp-content/uploads/2017/11/02.jpg)

This is what's problematic about this:

- Tether shows how centralized USDT is as a cryptocurrency. All decisions are in their hands, just like the issuance of new USDT is.
- Tether the company clearly show how much power they have over the software used to transfer the tokens. The fact that they were able to apply this fix so quickly and without community consensus, and managed to start pushing for exchanges to implement this software update, has all the hallmarks of a centralized corporation.
- Tether's ability to directly alter an account's ability to transfer funds lends itself to attack from government and regulatory institutions.

## Where to next?

The only way to make Tether secure is to add a layer of regulation on top, as explained [here][dkuna]. There's absolutely no chance of this happening, however - they'd never allow a full audit or regulatory supervision at this point. So, what can we expect in the future? Where do we find out more?

Given that we've been warning people about Bitfinex / Tether for a while now in [posts][fraud] and [live at conferences][f2], these slipups aren't surprising in the least, and we're only expecting things to get worse. If you'd like to find out more about the whole Bitfinex / Tether problem area, please see the below Youtube Hangout between Tone Vays, Jimmy Song, Bitfinexed, Flibber, and BTCVIX in which a lot is actually revealed about the trustworthyness or lack thereof towards Bitfinex. It's starting to sound a whole lot like MtGox again - the scandal in which the most popular Bitcoin exchange in the world just suddenly "lost" 800000 BTC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/TerIjELO7IY" frameborder="0" allowfullscreen></iframe>

To successfully defend against new MtGox scandals, our advice remains the same - keep your funds off of exchanges and [secure your private keys][secure].

Trade carefully!

[dkuna]: https://bitfalls.com/2017/10/31/dkuna-use-case-government-cryptocurrency-option/
[f2]: http://f2.bug.hr
[tether1]: https://bitfalls.com/2017/10/21/the-curious-tale-of-tethers/
[fraud]: https://bitfalls.com/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[omni]: http://www.omnilayer.org/
[secure]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[announced]: https://tether.to/tether-critical-announcement/