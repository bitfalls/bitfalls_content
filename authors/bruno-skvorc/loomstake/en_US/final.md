Many [blockchain](https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/) projects today offer a way to earn "interest" on your [cryptocurrency](https://bitfalls.com/2017/08/20/cryptocurrency/) holdings. Some rely on lending, like [Compound Finance](https://bitfalls.com/7h1n), while others implement staking mechanics.

## Staking

Staking a coin means putting some into the network as collateral and as a guarantee that you won't lie about decisions in that blockchain. You become a [validator](https://bitfalls.com/kxpz) and promise to process transactions truthfully. If other validators detect you're lying, your stake can be taken away. If you're telling the truth, you get a cut from new block rewards in this proof of stake network. That's how [Ethereum 2.0](https://our.status.im/tag/two-point-oh/) will work.

Staking is an excellent way of earning passive income in the blockchain space, but it's no secret that it requires both a significant capital up front and a high risk tolerance.

_Note: read more about Proof of Work vs Proof of Stake vs Proof of Authority in [this post](https://bitfalls.com/2018/04/24/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/)._

Staking is also how chains like Tezos and EOS work. However, these blockchains have not developed ways of supporting hundreds of thousands of validators and thus rely on a very limited circle of pre-authorized validators, similar to how things would work in a Proof of Authority network. Many cryptographic keys being authorized to vote requires a lot of computation - much more than it would take for the decision to reach everyone, so the network would fall out of sync. Add to that the sheer amount of transactions one would need to process in a network with few validators, and the hardware requirements become quite daunting as well.

This is where the concept of _delegation_ comes in. Delegation is the process of giving someone else your tokens so they vote in the network for you, and they kick back some of the profits to those who gave them the tokens to vote with.

While this Proof of Stake mechanic is most popular as a layer-1 security method for upcoming and certain current blockchains, it can also be useful as a means of securing individual apps, sidechains, or plasmachains - small sister chains which connect to the main chain of another blockchain. Such is the case with Aurora DAO which powers the IDEX exchange, and [Loom](https://bitfalls.com/2018/03/14/loom-token-lifelong-membership-loom-dappchains/), a company which maintains sidechains intended for high throughput and usability, as we [previously described](https://bitfalls.com/2018/08/25/plasma-update-loom-now-has-3-sidechains-in-production/).

## Staking with Loom

With Loom, you send your tokens into their smart contract and then decide who to delegate them to. There are several validators to choose from, all of which currently have the same kickback percentage: they take 25% of the profits and pass the rest onto you.

![](https://bitfalls.com/wp-content/uploads/2018/10/01-3.png)

Here's how this works. The initial estimate for earnings is presented in the following table taken from [this post on validation economics](https://medium.com/loom-network/plasmachain-validator-staking-economics-part-1-e816d5825849):

![Validator returns](https://cdn-images-1.medium.com/max/1200/1*ErH8YmYYXH_e7nFdnRT-Rw.png)

This is _before_ any validator fees - fees the validators you're delegating to collect for the service of staking your tokens for you. Those are currently 25% on every validator, as evident by the first image above. Additionally, there's a bonus applied for longer lock-up periods. Granted, this does mean your tokens are inaccessible for the duration of this lock-up period, but you also get higher returns. While this might make you miss the next Loom bull run and prevent you from selling high, it'll also guarantee longer term stable rewards. Weigh your options carefully.

Once you've been staking for a while, a reward will accumulate.

![Loom reward](https://bitfalls.com/wp-content/uploads/2018/10/02-1.png)

You can collect it and put it into your plasma chain deposit with the click of a single button.

![Reward deposited](https://bitfalls.com/wp-content/uploads/2018/10/04.png)

You can then choose to delegate that amount (update delegation), in essence getting compound returns.

![Stake dashboard](https://bitfalls.com/wp-content/uploads/2018/10/05.png)

![Updating delegation](https://bitfalls.com/wp-content/uploads/2018/10/06.png)

_Note that the UI is currently a little bugged in that it glows red when you try to enter an amount less than your originally delegated amount. Simply enter the re-delegation amount (in my case 814) and click the button, regardless of it glowing red._

Keep in mind that the lock-up period will reset if you delegate into the same pool you already delegated into previously, so if you've collected your 1-month reward in a 12 month lock up period and then delegated that reward with the same validator, your lock-up resets from the remaining 11 months to 12 months.

It's best to distribute delegations across multiple validators - this gives you a waterfall schedule of withdrawals while keeping the gains the same, and also insures you against a single validator going out of business or disappearing.

So does it actually work?

In the one month I've staked my 64.3k LOOM tokens, I gained a little over 800 LOOM tokens in return. That's a 1.25% monthly return, or if generously applied over a year it comes down to some 15% (accurate if you apply the 25% fee to the original estimate of 20% returns over a year with a 12 month lock-up), which is by far the largest staking return of any coin and chain today, despite [false reports claiming otherwise](https://cryptobriefing.com/tezos-most-profitable-staking/).

Based on my experience so far and the content produced by Loom as an organization bettering the blockchain ecosystem, I have confidence that staking with them is a good decision.