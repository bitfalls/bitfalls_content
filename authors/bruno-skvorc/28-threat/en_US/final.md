In May 2017, Maria Apostolaki, Aviv Zohar and Laurent Vanbever published a [paper] describing two new types of possible attacks on the Bitcoin network from the infrastructure angle. These attack vectors remain unresolved to this day.

In this article we'll briefly explain these attacks and the threat they pose. To better understand the terms presented below, it is recommended you read our introductions to both [cryptocurrency][cc] and [blockchain technology][bc].

## De(centralization)

As described in our [intro to nodes][nodes], there are only about 10000 Bitcoin nodes. 

![10000 nodes](https://bitfalls.com/wp-content/uploads/2017/11/02-3.png)

But according to Satoshi's original definition of a full node from the whitepaper, there are only around 20 *full nodes* (nodes that both mine and validate) on the network today - all of them [mining pools][pool].

Because of mining [competitiveness][pow] and the unprofitability of solo mining, as long as these big groups exist, small miners don't. They just send their machine's guesses into the pool without forming blocks by themselves - without having to decide which transactions to include in the blocks.

Mining is no longer decentralized.

To keep the network decentralized, we rely on [validation nodes][nodes] which validate the "products" of mining nodes. But most Bitcoin users simply aren't willing or able to maintain their own node at home because it's just too complex and expensive - just running [Bitcoin Core][bcore] (the usual validation node software) requires around 150 GB of hard drive space and 2GB of RAM.

This obstacle is the reason why most end-users pick simpler ways of keeping their cryptocurrency safe - [paper wallets][paperwallet], hardware wallets like the [Ledger][ledger], or even centralized services and crypto-banks like Bittrex, Coinbase, etc. None of these approaches constitute a node. Coinbase has its own node, sure, but all its users are simply connecting to that one, not running their own. Most participants of the Bitcoin ecosystem don't contribute to the network in any way at all, which is why out of the millions of BTC users around the world, only 10000 run nodes.

So if mining is centralized and validation isn't as decentralized as it should be, how can the system even still be alive and kicking if it's working against all the concepts laid out in the original whitepaper? Is there even any danger at all if we're apparently immune to the breaking of Bitcoin's fundamental concepts?

## Attacks

The problem is actually very, very real. Besides the [standard ways of putting a stop to Bitcoin][unstop], the authors of the aforementioned [paper] dug out the following worrying figures:

- only 13 of the world's ISPs host 30% of the Bitcoin network's nodes.

  ![30% of the network on 13 ISPs](https://bitfalls.com/wp-content/uploads/2017/11/01-5.png)
  
- 60% of all Bitcoin traffic is passing through 3 of those 13 ISPs

  ![60% of the network going through 3 ISPs](https://bitfalls.com/wp-content/uploads/2017/11/04-1.png)

These numbers mean a different kind of centralization: centralization of internet traffic. Such centralization makes a BGP hijack attack possible.

### BGP

BGP or _Border Gateway Protocol_ is a network standard routers use to share information about how to reach certain IP addresses when looking for a device on the internet.

A BGP hijack happens when an ISP gives out false information to divert the traffic, thereby stealing the traffic of another internet-connected device. These attacks are fairly common and the biggest one in the Bitcoin space was a whopping 447 nodes in 2015 when there were only around 5000 of them, so a scale of almost 10%.

What can such routing attacks actually do, though?

### Network Fragmentation

In Bitcoin, all nodes communicate with one another. But since so many of them are on so few ISPs, preventing the communication between two such services would cause a chain split to occur in which each chain would continue developing on its own. 

The Bitcoin protocol is envisioned in such a way that nodes that go missing in a network are simply ignored. They are considered dead, so the rest of the "living" ones keep on chugging along. But if both chains think the other is dead, each keeps growing on its own. Since the protocol is designed to mitigate such communication outages by simply eradicating the changes of the chain that grew the least since the split occurred, this means the following:

- the chain that grew least would lose all BTC [block rewards][rew] given to the miners as a result of discovering blocks
- the chain that grew least would lose all transactions from those lost blocks, effectively undoing a certain period of trading and BTC usage in that part of the network.

This attack can be not only extremely expensive to miners, but also catastrophic to companies which use Bitcoin in their day-to-day trading or payment operations.

### Delay Attack

This attack targets a specific node which, as we noted earlier, can be a big pool miner which encompasses 1/20th of the network's hashing power. This is the process:

- node A sends block information to node B as per node B's request
- the attacker intercepts this request, and sends an older block from A instead
- node B checks the old block in futility, and just before 20 minutes elapse, the attacker triggers another send, this time real, keeping the connection alive.

Because of programmatic limitations in Bitcoin's protocol, one node does't disconnect from the other unless they've been miscommunicating for 20 minutes. The attacker avoids this timeout on purpose, making node B do futile work.

The consequences of such an attack can be a large futile expense to a miner, preventing of validation when blocking validation nodes - which can prevent nodes from signaling their desire for a software update on the Bitcoin protocol (see [forks]) - or even a _double spend_ error. With a _double spend_ error, it's possible to spend the same funds twice, because the initial transaction hasn't been processed yet, but has been broadcast.

## Conclusion

More and more signs of Bitcoin's vulnerability appear every day, demonstrating that it's both [stoppable][unstop] and censorable.

The best defense against such losses of value are:

- store your currency offline, and away from centralized services and crypto banks like Coinbase. Whenever your currency is stored on a service or device with internet access, you're in danger of losing it.
- If you have the financial ability to do so, please run a validation node at home and help the decentralization of the Bitcoin network.

The problems we outlined above are particularly important these days as Bitcoin prices climb to their all time high levels and more and more mainstream "civilians" enter _the game_. Without adequate precaution, too many people are at risk of losing much of their hard earned money.

_For the curious, a programmed prototype of the attack described above is available [here][repo]._

[paper]: https://btc-hijack.ethz.ch/files/btc_hijack.pdf
[page]: https://btc-hijack.ethz.ch/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[nodes]: https://bitfalls.com/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[pool]: https://bitfalls.com/glossary/#mining-pools
[rew]: https://bitfalls.com/glossary/#block-reward
[ledger]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[paperwallet]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[address]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[forks]: https://bitfalls.com/2017/11/07/segwit2x-fork-can-expect-whos-behind/
[unstop]: https://bitfalls.com/2017/08/21/is-bitcoin-unstoppable/
[pow]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[bcore]: https://bitcoin.org/en/download
[repo]: https://github.com/nsg-ethz/hijack-btc/tree/master/delay_attack