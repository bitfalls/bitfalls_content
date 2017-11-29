You'll often hear the word _node_ thrown around in blockchain and [cryptocurrency][cc] circles. If you've read our [intro to blockchain][bc] (and we highly recommend you do that), one of the characters in the comic there that's writing down transactions on a piece of paper is actually _a node_. That introduction is quite simplified, however - let's explain the concept of nodes in a bit more detail now.

## Validation Nodes

One node is a computer running specific software. In the case of Bitcoin, one node is a Bitcoin program which connects to other Bitcoin nodes, i.e. other Bitcoin programs on the same machine, or on other machines which can be across the street or on the other side of the planet. There are several types and several versions of Bitcoin software. By picking a specific version of a specific Bitcoin program, a user "votes" for certain changes in the Bitcoin protocol. For example, if a bunch of users suggest the increase of [21 million total BTC to 42 million][finite], the majority of the network is required to vote "yes" by installing the software implementing this change. Code changes are, thus, democratic.

Where this idea falls apart is the fact that there are very few Bitcoin nodes out there: a mere 10000 currently.

![10000 Bitcoin nodes](https://bitfalls.com/wp-content/uploads/2017/11/01-4.png)

... whereas [Ethereum][eth], a cryptocurrency 5 years younger, already has twice as many:

![20000 Ethereum nodes](https://bitfalls.com/wp-content/uploads/2017/11/02-2.png)

Neither number is very impressive from a global perspective. According to [some calculations][awsnode], running a Bitcoin node on AWS (Amazon's cloud service) costs around $10 per month. This means that taking over 10000 brand new nodes takes $100,000 per month, or only $1.2m per year - pocket change to any [Bitcoin early adopter][finite].

A list of node software you can install, along with their pros, cons, and special features, can be found [here][list].

It's important to note that validation nodes are purely an expense for the users running them. They give their users nothing. Bitcoin Core, for example, needs around 150 GB of disk space, 2GB of RAM, and a fast and uncapped internet connection with at least 50 kb of constant upload speed available just to run. It's not uncommon to need to upload over 200 GB of traffic per month when running a single node. Validation nodes are volunteer nodes and are useful for the system's decentralization, but as they become ever more expensive to run, so too does the number of nodes drop. Add to that the mounting disillusion with Bitcoin's theoretical decentralization due to the fact that [bankers seem to have taken over the protocol's development][bankers], and the fact that Bitcoin's price is being pumped by [crime syndicates][tether], and it's no surprise that the number of nodes dropped by 20% in a single month - from 12000 to 10000. As more nodes disappear, so does centralization. A hostile takeover becomes more and more probable.

## Mining Nodes

A mining node is a validation node which also uses the hardware of your own or a rented machine to guess the combinations of numbers and letters needed to validate and verify a [block]. A mining node can _team up_ with other nodes and send guesses to a common pool ([pool mining][pool]) to increase chances of guessing, but then counts as only one node.

Because most new miners opt to join a powerful pool to maximize their chances of mining a block and getting rewards, we're seeing a very serious technological centralization happening in which 20 of the most powerful pools are mining almost all the Bitcoin.

Here's [a list][pool-list] of the biggest mining pools - notice that the first one mines 25% of all the bitcoin in existence.

![Antpool facility](https://bitfalls.com/wp-content/uploads/2017/11/03-2.png)

A mining node is the only bit of software which can "produce" new Bitcoin, and running one in a way that makes it worth your while requires either a very strong computer or free electricity. If you'd like to give mining a go, the list of BTC mining software can be found [here][minesoft].

## Conclusion

A mining node is a node which contributes to the network by guessing the combinations needed to "seal" the blocks of transactions and thus confirm them, producing new Bitcoins in the process. A validation node is a node which validates this information, makes sure it's true, and passes the information along to other nodes, thus enabling the transfer of monetary value from location A to location B. Mining nodes are a _subset_ of validation nodes because every mining node is also a validation node.

This difference is only manifested in the [PoW] consensus system and becomes technically unnecessary in PoS. With PoS every node can be a validation node, and mining nodes as such no longer exist - new tokens are created based on another principle. For more about this, please read our [PoW vs. PoS article][pow].

[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[pow]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[awsnode]: http://calculator.s3.amazonaws.com/index.html#r=IAD&s=EC2&key=calc-7C655B73-FA35-40F0-9518-4773E3E4A8C7
[list]: https://en.bitcoin.it/wiki/Clients
[block]: https://bitfalls.com/glossary/#block
[pool]: https://bitfalls.com/glossary/#mining-pools
[pool-list]: https://www.buybitcoinworldwide.com/mining/pools/
[bankers]: https://np.reddit.com/r/btc/comments/743qb8/is_segwit2x_the_real_banker_takeover/
[tether]: https://bitfalls.com/2017/10/21/the-curious-tale-of-tethers/
[minesoft]: http://www.bitcoinx.com/bitcoin-mining-software/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/