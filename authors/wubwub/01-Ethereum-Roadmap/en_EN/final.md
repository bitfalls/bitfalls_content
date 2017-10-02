The [Ethereum] project, although full of potential, is still in its infancy. The two-year-old cryptocurrency still matures technologically at the hand of its creator Vitalik Buterin and his team of developers, and they do not plan to stop anytime soon.

The Ethereum project is divided into 4 stages of development:

  1. Frontier
  2. Homestead (the current phase)
  3. Metropolis
  4. Serenity

## Frontier

Frontier was the first phase of Ethereum development, launched in July 2015.
It was intended primarily for people with a technical background, considering that interaction with the network itself was done primarily through the command line (an interface not all people are familiar with).

 Frontier was a bare-bones network made of basic parts needed for it to function. The purpose was to develop and test decentralized applications, to test different tools, and to start mining Ether.

## Homestead

Homestead is the second phase of Ethereum's development, launched on March 14th 2016 (Pi day). It activated on block 1,150,000 and it brings many protocol improvements which lay the foundations to future upgrades and for speeding up the transactions on the network.

## Metropolis

The third Ethereum phase is very interesting and brings us many changes and novelties like security updates, smart contracts getting smarter, and permitting a larger degree of automation. Metropolis also makes using Ethereum easier for "regular" people with light clients (programs which do not need the whole blockchain downloaded locally, which could take a hundreds of gigs) like [Status] for iOS and Android devices.

### Ice age

The so-called "Ice age" is an initiative which will disable mining with graphics cards in the Proof of Work (PoW) consensus mode with the intention of using a more economical approach with a Proof of Stake (PoS) consensus. 

*Proof of Stake will be explained in the Serenity part below*

The PoS mode stems from the stalemate of development in the Bitcoin community due to disagreements between the miners and the core development team (a group of programmers that work on the Bitcoin protocol). This disagreement brought on a two-year bickering about improving the scalability and permeability of the Bitcoin [blockchain]. Bitcoin transaction fees grew to outrageous proportions from $5 to $100 or even more for sending just a few USD, depending on the current network traffic.

Ethereum developers thus implemented the _Ice age_, so people wouldn't have a choice other than to accept the PoS consensus, thereby preventing miners from holding the project hostage and holding the development back like it was the case with Bitcoin.

In time, the ice age will raise the difficulty of mining and slow down the production of blocks until the network is completely frozen and unusable, hence the name.

With _Metropolis_, the beginning of the _ice age_ is postponed by 18 months, and the miner reward has been decreased from 5 Ether every ~20 seconds (which is the block interval) to 3 Ethers per block, as a preparation for PoS when the reward will decrease even more.

### ZK-Snarks

ZK-Snarks (Zero-Knowledge proof) is the technology behind a cryptocurrency called Zcash. It enables validators to verify the transaction without processing it, so they don't need to know what is in the transaction, only whether it's valid or not. In other words, ZK-Snarks enable anonymous transactions on Ethereum. In particular, the principle of  _zero knowledge_ is described as "I know something happened, I can prove that something happened, but I don't know what happened."

 ![Ethereum and ZCash logo](https://bitfalls.com/wp-content/uploads/2017/10/Eth_Zcash-2.png)

Since Ethereum is a public blockchain, the companies who want to implement the Ethereum blockchain in their business are afraid to put potentially sensitive and confidential data onto the blockchain. In this case, the ZK-Snarks would allow for privacy of sensitive data.

### Byzantium and Constantinople

The Metropolis upgrade will be split into two stages, that is, two separate upgrades called  Byzantium and Constantinople.

The first upgrade _Byzantium_ contains EIP-s (Ethereum Improvement Proposal) 100, 140, 196, 197, 198, 211, 214, 649 i 658. Constantinople brings EIP 86 and 96.

[See what every EIP brings in this list][eips]

Byzantium is currently in its testing period on the Ropsten testnet. The testing period should last between 2-4 weeks, and if everything is in order, we can expect it to be on the main net around the end of October 2017.

## Serenity

### Casper Proof of Stake
                                
The last phase of Ethereum's development - _Serenity_ - will bring us the long-awaited Proof of Stake consensus. The main difference between PoW and PoS is that PoW uses powerful hardware which calculates the  [block hashes][hash] and validates blocks and transactions. As the name says: in Proof of Work, the machines invest time and work to get the right hash.

In Proof of Stake, the mining is virtual. The validator (the one who confirms validity of transactions by [sealing the blocks][blockchain]) sends a special transaction into the blockchain which will lock up their Ether for a certain time. It can be considered a bank deposit on which you earn interest.

Essentially, the validators are betting which block will be appended to the blockchain next. If a validator plays by the protocol rules and includes legitimate transactions in the block, they get dividends. If a validator wants to include illegitimate transactions in the block, they lose the staked Ether. This way, every attempt at cheating or sabotaging the network has significant financial consequences.

### How is PoS better than PoW?

* There is no need to spend large quantities of electricity. It's estimated that the daily cost of mining Bitcoin and Ethereum right now is over a million dollars in electricity and hardware.

* With decreased electricity consumption, we can reduce inflation in a way that we reduce the issuance of the new coins and create an equilibrium between the newly created coins and coins that are lost or destroyed over time. We could even have [deflation][defl].

* PoS is fighting against mining centralization, which has become apparent with Bitcoin in China. Also, PoS also prevents miners from damaging the network, something we also saw done in Bitcoin.

* [51% attacks] in which the attacker tries to take over the network by having more than 51% of the hashing power will become enormously more expensive than in PoW. The attacker has to have 51% of the cryptocurrency in circulation among the validators. If the potential attacker really has that much money, it would be more feasible for them to retire and forget all about cryptocurrency. Otherwise, they could lose it all and things would continue as usual anyway.


### Sharding

Every blockchain has the same weakness, and that's scalability. When a blockchain hits the saturation point and there are more transactions than the network can process, the speed of processing them declines, something akin to a road going from four lanes to two lanes.

As the road narrows, a traffic jam forms. In the same way, transactions can't fit into a block and have to wait their turn. An even more pressing problem is that the one who pays a bigger transaction fee has the higher priority. This not only means that the network is slowed down, but it gets more expensive to transact for everyone.

*In comparison, Bitcoin can process ~3-7 transactions per second, while Ethereum can process ~7-15.*

The basic idea behind sharding is to slice the blockchain up into a lot of small parts, "shards."

An example of sharding on Ethereum would look like this: every address that begins with  0x00 is put into one shard, every address that begins with 0x001 is put into another shard and so on.
This lets us process transactions in a parallel manner, instead of a serial manner.

Note that currently, every full blockchain node (every miner) has to synchronize the whole network starting with the [Genesis block][genesis] and then, as the network synchronizes, the node executes and checks every transaction that ever happened on the blockchain.

With sharding, every node in a particular shard verifies just that shard. This allows us to speed up the transaction throughput because the nodes don't have to verify the whole blockchain, but rather just a part of it, depending on the shard a node belongs to. Of course, sharding would have a positive impact on the disk space of the node, too.

Sharding is still in development. We expect it to be deployed along with Casper in the Serenity upgrade.

## Raiden Network

The Raiden network is an off-chain solution for increasing scalability on Ethereum.
Off-chain means that the Raiden infrastructure is built upon Ethereum, but it's not connected to the blockchain per se. Raiden brings nearly instant transactions of  [ERC20 tokens] without the regular need for global blockchain consensus. This is possible due to digitally signed transfers called **balance proofs**.

Raiden functions in a way that two parties open a "payment channel" which enables two-way payments with very small and few fees.

Let's say that Mark and Steve both have 200 tokens on the channel.

Mark sends 150 tokens to Steve as payment for a service, the payment channel records that, and Steve now has 350 tokens.

Steve sends 25 tokens to Mark, the payment channel records that, and Steve now has 325 tokens, while Mark has 75 tokens.

Mark again sends 50 tokens to Steve, Steve then sends 100 tokens to Mark. To keep it simple, we'll stop here and assume they've finished their business and they close the payment channel.

The payment channel calculates the difference and only two transactions are sent to the blockchain:

Steve sent 125 tokens to Mark. 

Mark sent 200 tokens to Steve.

End balance:

Steve has: 275 tokens.

Mark has: 125 tokens.

Payment channels are useful when microtransacting. Sending hundreds of transactions of 10 cents for example, and paying a fee for each of those, plus waiting for every transaction to be mined isn't really feasible. It's far more effective to use the Raiden payment channels and then send it all in just one transaction to the blockchain. 

## Conclusion

There's a lot of development still to be done in Ethereum, and it'll take years until we have a finished product. But the whole crypto industry is still in its infancy, and we can expect great things as the blockchain technology advances. The blockchain disrupted a lot of industries that functioned on outdated principles, and this is truly the beginning of a new chapter of history.







[Ethereum]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/

[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/

[hash]: https://bitfalls.com/glossary/#hash
[Status]: https://status.im
[defl]: https://bitfalls.com/glossary/#deflation
[genesis]: https://bitfalls.com/glossary/#genesis-block
[eips]: https://github.com/ethereum/EIPs#accepted-eips-planned-for-adoption

[ERC20 tokens]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/

[51% attacks]: https://bitfalls.com/glossary/#51-attack
