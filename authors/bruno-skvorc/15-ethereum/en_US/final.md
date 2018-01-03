_In this article we'll explain Ethereum in a newbie-friendly way, and compare it to the most popular cryptocurrency in the world: bitcoin. The article was written with the uninitiated in mind, but it's still highly recommended you read our [introduction to cryptocurrency][cc] and [introduction to blockchain][bc] before continuing in order to be able to better absorb the content that follows._

---

Ethereum, launched in 2015 by Vitalik Buterin, is a special [blockchain][bc] with a special token called Ether (the ETH symbol in exchanges). Ether is used as fuel (literally, _gas_) to power the Ethereum network and execute _smart contracts_ (see below). Ether is paid to miners (the people running the network) in _gas cost_ to make the features below possible, and thus isn't a crypto**currency** as much as crypto**oil**.

Here's how it's different from bitcoin, and what makes it stand out in the world of cryptocurrency.

## Finality

Bitcoin has a [theoretical limit of 21 million bitcoins ever produced][finite] which makes it a deflationary currency: its total amount in circulation shrinks over time as people lose access to their [wallet], stockpile it, etc.

Ether has no limit, but does have a fixed ratio of production. Currently a little over 15.5 million Ether is mined every year, which comes down to 5 ETH every second. Far more than bitcoin's current rate of 25 BTC every 10 minutes or so. After Ethereum switches its mining type - more accurately known as consensus type - to PoS (see below), the production rate will decrease dramatically, approaching zero.

![Coinmarketcap graph of Ethereum currently](https://bitfalls.com/wp-content/uploads/2017/09/01-3.png)

All this will make Ethereum's value stop [growing disproportionately][bubble], thus reaching market price stability which lends itself perfectly to the practical uses described below.

## Smart Contracts

Bitcoin supports simple scripting. For example, you can write a small program with bitcoin which will support transactions that have multiple addresses as input, or that need multi-sig (a signature from several people before funds are released). The language used for this is not _Turing complete_, however, because it doesn't have _loops_ (if you don't know what this means, it doesn't matter).

Ethereum programs on the other hand are programmed in Solidity - a language that _is_ Turing complete, thus allowing for any kind of program to be written in it, given enough resources (within reason). When a program is written in Solidity, it needs to get sent to the blockchain, which costs _gas_, paid in Ether. The bigger and more complex the program, the more expensive it is to _deploy_ it to the blockchain. Thus, inefficiency costs money - it is in the interest of everyone involved to keep those programs as small as possible.

Vitalik himself best describes the smart contracts with a vending machine analogy:

"_A vending machine [...] basically implements the conditions of some kind of an agreement. And the conditions of the agreement here are simple. You put $2 in, water comes out. You do not put $2 in, water does not come out. If you do not put $2 in but water does come out then that's bad. And a vending machine is basically an encoding of this set of rules, that also comes with a mechanism that keeps it at least kind of secure. Secure enough for $2 water bottles._"

<iframe width="560" height="315" src="https://www.youtube.com/embed/r0S4qIMf4Pg" frameborder="0" allowfullscreen></iframe>

When we pay an amount of Ether into a smart contract, that smart contract can then decide what to do with this Ether - send it to address A based on one condition, address B based on another, lock it in place for a period of time, refund it, move it around based on external input, trigger external output based on this Ether, etc.

A practical example would be replicating Kickstarter. Kickstarter is a site which lets creators gather funds for their projects before they're launched. The basic rule is, if a given amount of money is exceeded in a given number of days, the project was a success and the money can be released to the makers. Otherwise, the money is refunded. This simple condition is very easy to replicate with smart contracts, eliminating human error, greed, and the middleman from the equation, offering up a truly decentralized way of fundraising.

Applications built with smart contracts are called decentralized apps or _dapps_.

## What are ERC20 Tokens?

A very important feature of Ethereum is the ability to create new tokens on the Ethereum blockchain. Tokens are a "cryptocurrency" of sorts built with specific smart contracts, and used like any other - sending to and from addresses. These tokens are sent to Ethereum addresses, not [addresses][wallet1] of a new cryptocurrency's blockchain. It is because of this that tokens aren't really a cryptocurrency per se, but the result of logic executed via a smart contract. Saying a token is a cryptocurrency is actually just as inaccurate as claiming that a program is a programming language.

A token can be a concert ticket, loyalty points in a shop, in-game currency, etc.

![A loyalty card](https://bitfalls.com/wp-content/uploads/2017/09/02-3.jpg)

As more and more tokens started to appear, their format was standardized into [ERC20][erc20]  - a set of rules on how to develop them to make them easily consumable by various exchanges and systems. This means that all ERC20 tokens have some common features like a ticker symbol for exchanges, an icon, etc. making them easy to list on various websites by reusing the same code used for a previous ERC20 token.

Creating ERC20 tokens in combination with smart contracts is Ethereum's revolutionary feature which is poised to completely change the way we do business. Tokens make autonomous companies possible, they allow for partial purchases of digital goods or land, they even allow for the creation of autonomous cars which drive themselves, pick up customers, drop them off, collect payment, and effectively _pay themselves off_. The number of potential use cases is so large we haven't even scratched the surface.

## PoS

The third biggest difference from bitcoin is that Ethereum will be moving to an alternative way of _mining_ called PoS (Proof of Stake) rather than PoW (Proof of Work).

With [bitcoin][bc], a unit of proof of work is the hash gained by doing massive calculations. We'll publish a separate post about PoW and PoS soon, but for now suffice it to say that a PoS system isn't wasteful as far as electricity goes, which is an important feature considering [China's mining dominance][finite].

![Cryptocurrency mining farm](https://bitfalls.com/wp-content/uploads/2017/09/03-3.jpg)

PoS has its own problems, of course. In this system, a user of Ethereum trying to be a _node_ (this new type of miner) _stakes_ their Ether to guarantee the correctness of their calculations. If they try to game the system and fake some calculations that aren't valid, the other nodes will call the node out, and the stake gets lost. Otherwise, the staker gets their stake back after a few months (yes, months!) plus any fee earnings they scored from transactions or from executing smart contracts. The size of the stake deters malicious actors - the initial stake is said to be 1000 Ether.

## Conclusion

To sum up, Ethereum differs from Bitcoin in the following ways:

- it'll soon transition to [Proof of Stake][pos] instead of [Proof of Work][pow]
- it'll soon be quantum-proof (we're working on a post about this)
- it supports the creation of sub-tokens on the network (instructions on making your own coming up in an article soon!)
- it supports custom logic in the blockchain for full financial automation (smart contracts)

There's another simile we like to mention when talking about BTC vs. ETH:

- Bitcoin is gold. It's complicated to obtain, expensive and slow to transfer, but highly deflationary and finite ([for now][finite]). This makes it a good long-term investment, depending on who you're asking.
- Ethereum isn't silver to Bitcoin's gold as many would assume. Ethereum is oil. Other products are made with the help of Ethereum, and ERC20 tokens correspond to plastics, make-up, paint, rubber... Ethereum is the base of an entire new industry and while there are several alternatives (Tezos, EOS, Rootstock, NEO), none of them have a developer or user community as wide and strong as Ethereum does.

If you'd like to buy or sell Ethereum, be sure to [let us know][mail]. We welcome any comments or questions, please leave them in the comment section below!

[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[bubble]: https://bitfalls.com/2017/09/06/bitcoin-bubble/
[wallet]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet1]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[mail]: mailto:contact@bitfalls.com
[erc20]: https://github.com/ethereum/EIPs/pull/610
[pos]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[pow]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
