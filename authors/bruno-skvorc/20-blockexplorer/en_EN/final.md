In a [previous post][anon], we explained how public Bitcoin's transactions are, and how easy they are to track. In this post, we'll take a look at how to track them, and how to interpret the information the web interface provides us with.

## Blockexplorer

There are many websites for exploring the Bitcoin [blockchain][bc], but [Blockexplorer][be] is probably the most popular one.

![Blockexplorer input field](https://bitfalls.com/wp-content/uploads/2017/10/01.png)

You can punch in the following values:

- to check transactions, you enter a transaction [hash] like this one: 57309a5cf004fd4746ab508deb0093a5181fb93ead1fbf0b0ebf375b2e817fb6.
- the [public key][wallet] of an address to find out this address' status and balance, as well as see transactions that have the address as an entry or exit point.
- the number of a [block] you want to explore to find out when it was [mined][mining], what data it confirmed, and so on.

As an example, let's take a look at the aforementioned transaction. Copy the following into the field and confirm: 57309a5cf004fd4746ab508deb0093a5181fb93ead1fbf0b0ebf375b2e817fb6

This is the identification hash of the transaction. Once you confirm, Blockexplorer will return all information related to it.

## Analyzing the Transaction

The upper section of the screen will contain basic transaction information.

![Basic transaction information](https://bitfalls.com/wp-content/uploads/2017/10/02.png)

The table tells us the following:

- how big the transaction was, in bytes. This one was 3873. If we consider the fact that Bitcoin's blocks are currently capped at 1MB, that means a single block can contain about 258 such transactions. If we know that a new block is mined approximately every 10 minutes, we can conclude that the Bitcoin protocol has a 2-3 transactions per second capacity. Far from the several thousand per second Visa currently executes.
- Fee rate is the fee that was paid by the user generating the transaction in order to broadcast it to the BTC network and have it confirmed. The fee is given to the miner who mined the block. At 0.001305959204750839 BTC / kB (1 kB = 1000 bytes), this means this transaction cost 0.00505798 or $22.2 at the current BTC price of $4368.
- Received Time and Mined Time are usually identical and signify when the block was accepted into the blockchain and when it was mined respectively.
- _Included in block_ is the ID of the block in which this transaction was confirmed. Remember - mining is a competitive sport. Several extremely powerful computers are competing in who will guess a nonce (a random number) first, because the winner gets both the transaction fees from all transactions in a block _and_ the [newly minted Bitcoins][bc]. We'll take a look at this block later.

![Detailed table](https://bitfalls.com/wp-content/uploads/2017/10/03.png)

The detailed table below (which stretches to the bottom of the screen and can be expanded by clicking "Show More") contains all the Bitcoin movement in this one transaction.

When sending Bitcoins, it's possible to have several input addresses, and several output addresses. Many [wallets][wallet] automate this process and show the user only one amount, but this amount is actually saved on several addresses on a [device][ledger] or software wallet.

When a user wants to send Bitcoins, they can send them to one address, or to several addresses at once, saving money and time. Furthermore, because of [Bitcoin's non-anonimity][anon], it is often recommended to use a new address after every transaction. This address is called a _change address_ because it contains the leftover money from a transaction. The previous address is thereby completely drained and can be discarded. In this case, the transaction was initiated by an exchange (Bitstamp), which is why the number of destination addresses is so large.

The table's left side contains input addresses, and the right side contains the destination addresses. It is not known which amount from which address ended up on which address - only the total tally and distribution are known.

In the rightmost column, there's a parenthesized letter `S` or `U`. `S` stands for "spent", and `U` stands for "unspent". Unspent simply means the money is still in that address.

At the bottom of the screen, we can see the sums of different attributes in this transaction.

![The bottom of the table](https://bitfalls.com/wp-content/uploads/2017/10/04.png)

Specifically, we see:

- how many confirmations a block has had so far. Remember, when a block is [mined][bc], the data is sent to all other computers on the network so that they may continue building the blockchain on top of the last block that was sent in. The higher this number is, the more "baked in" your transaction is - it exists on many computers, ergo, it cannot be undone, invalidated, or corrupted.
- the total number of Bitcoins transferred in this one transaction. Since the initiator of the transaction is an exchange, it's normal for the amount to be a little bigger. In this case, it turns out the exchange sent $167,312.42 at a transaction fee of $22.20. That's 0.0001326859 - a little more than one-hundreth of a percent.

## Analyzing the Block

If you now click the [hash][hash] of the block in the first table on the transaction screen, or if you enter the block's number into the input field (487978), you'll see the block's full data.

![A block's first table](https://bitfalls.com/wp-content/uploads/2017/10/05.png)

The table itself is preceded by the `BlockHash` - an identification hash for  block 487978. Any of these two values can be punched into the input field and will lead to this same screen. If you want to know how this hash was calculate, see [this post][bc].

Under `Summary`, we can see the following information:

- Number of transactions indicates the total number of transactions included in this block. It's important to note that transactions are usually much smaller than our original transaction above, so many more than 258 can fit inside a 1MB block. In this one, 2712 were processed.
- Height - the block's ordinal number
- Block reward - the [reward][reward] given to the miner who mined the block. That's currently 12.5 BTC, or a little above $53,000. This does not include transaction fees, which are added to the 12.5 [virgin coins][reward].
- Timestamp is the exact moment of this block's hash discovery.
- "Mined by" is the ID of the miner responsible. Some miners, like individuals, small companies, or government agencies who would prefer to stay anonymous, do not identify themselves (identification is optional) - that's why this field is empty here. As an example, one of the biggest miners in the world is the company Bitmain which produces [ASIC] machines called AntMiner. That's also how they identify in the block mining process. If you take a look at the [recent blocks list][blockslist], you'll notice how much they dominate the mining process.
- Merkle Root is the [hash] of all transactions from this block, and their order. The Merkle Root is used when validating the block's *content*, not the transactions themselves.
- Next and Previous block lead to the next and previous block's info screen, predictably.
- Difficulty is a mathematical value of how hard it is to find a valid hash for this block. [Difficulty][diff] auto-adjusts every 2016 blocks for balance as new blocks are mined in order to maintain the block per 10 minute average, and every new block is harder to mine than the last. Sometimes, difficulty can go down, like if some miners leave the network.
- Bits are a hexadecimal representation of the difficulty. Every block stores the compressed form of its difficulty in the form of Bits, calculated with [this algorithm][bits].
- Size denotes the total size of the block. In this case, we're dealing with 991124, or little under a megabyte: 0.991MB. That's almost a completely full block. A block does not have to be at 100% capacity to be mined. In fact, empty blocks can be mined in moments of extreme network inactivity. The miners never stop, regardless of network needs.
- Version is a set of numbers which the miner software uses to [signal the rest][version] of the network about its intention to adopt certain updates to the network.
- Nonce is the random number added to the combination of transactions, their data, the Merkle root, and other bits of information in order to make the [PoW][pow] algorithm come up with a hash that matches the difficulty. The end goal is to get a hash that's smaller than this difficulty, usually indicated by the number of leading zeroes in a hash. Once such a hash is calculated, the nonce is considered the solution, and used as a confirmation mechanism for other nodes (miners) in the network which then confirm that the block is indeed valid.

In the table below, we can see all the transactions in this block. As mentioned earlier, transactions are usually much smaller than the one from our first example, so here we can see many transactions with just one input address and one or two output addresses. Let's look at these three:

![Three transactions of a block](https://bitfalls.com/wp-content/uploads/2017/10/06.png)

The first transactions sends 29.44 BTC to two addresses. Seeing as neither amount is a rounded number, and the bigger amount is already spent (`S`), we can assume a fiat value was the target of the transaction. If we take a look at the date - October 2nd - and check BTC price that day ($4400), we can conclude that the amount was a round $130,000. The other address is obviously a _change address_.

Let's look at the next two transactions now. Both have the same input address, and both times the user is sending 0.5 BTC. The amount is sent to two other addresses in both cases, split into equal parts. We can see that the round number (0.25) was immediately spent (`S`), while 0.2485 from each transaction was kept at the receiving address. The reason why it's not also 0.25 is the transaction fee in the bottom left corner of the transaction frame on the screen - the sending of this amount cost the user 0.0015 BTC.

Let's look at those addresses now.

## Analyzing the Address

If we click any of these addresses, we'll get their information screen. Let's first look at the input address of the previously discussed two transactions: `1ArB3Sn8kNt236fh1CHcvYaEz7RnnV9qq7`.

![The input address](https://bitfalls.com/wp-content/uploads/2017/10/07.png)

We can see that this address was used to move a total of 12.4 BTC: 7.37 received, and 5.03 sent through 28 transactions. The remaining balance is 2.34 at the time of writing.

This address' owner is trying hard to keep amounts rounded, aiming for 0.5 BTC. They frequently use the same change address: `1CBk5dAsbC3ZzDSLC2nBq9kYXjfvQk5WGZ`. The address is also one of the two output addresses in the previously discussed transactions. Thus, we can conclude that this is the address our user is using to continue participating in the network, while the others are probably their clients or [HODLing][hodl] acquaintances.

If we check where the address we're currently inspecting got its funds, we'll notice it frequently received from multi-inputs and was part of multi-outputs, which usually means it's an exchange or a tumbler - a service used to "launder" BTC. It does this by putting everyone's BTC into a common pool, and sending from that pool to new addresses, so no one can tell who's who after this multi-directional transaction.

If we check the change address mentioned above, we'll notice it had 33.44 BTC of traffic in its 95 lifetime transactions, with both single and multi inputs and outputs. Given that both ends of this transaction have multi-inputs and multi-outputs, it's likely we're dealing with either a tumbler, an exchange, or a [whale] who is using a multi-address [wallet].

## Alternatives

Alternatives to Blockexplorer (besides their own API which lets you connect to blockchain data directly) include the following services (many of which have their own API on offer):

- https://tradeblock.com
- https://insight.bitpay.com/
- https://chain.so/
- https://www.blocktrail.com/
- https://www.walletexplorer.com/
- https://bitcoinchain.com/block_explorer
- https://live.blockcypher.com/btc/
- https://bitinfocharts.com/bitcoin/explorer/
- https://www.coinprism.info/
- http://srv1.yogh.io/
- https://www.smartbit.com.au/
- http://explorer.coinpayments.net/index.php?chain=1
- https://webbtc.com/

## Conclusion

Reading blockchain data might be confusing at first, but once you know what each bit of data means, everything falls into place. With this newfound knowledge in tandem with techniques described in [this post about Bitcoin's anonymity][anon], you can easily track a user or address across the blockchain, and take note of all their transactions. Try it on some publicly available addresses - find some on forums or platforms like [Steemit][steem] where people like to beg for donations.

[anon]: https://bitfalls.com/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[be]: https://blockexplorer.com
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[block]: https://bitfalls.com/glossary/#block
[mining]: https://bitfalls.com/glossary/#mining
[ledger]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[hash]: https://bitfalls.com/glossary/#hash
[virgin]: https://bitfalls.com/glossary/#virgin-coins
[reward]: https://bitfalls.com/glossary/#block-reward
[blockslist]: https://blockexplorer.com/blocks
[diff]: https://bitfalls.com/glossary/#difficulty
[bits]: https://stackoverflow.com/questions/22059359/trying-to-understand-nbits-value-from-stratum-protocol/22161019#22161019
[version]: https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki
[hodl]: https://bitfalls.com/glossary/#hodl
[whale]: https://bitfalls.com/glossary/#whale
[asic]: https://bitfalls.com/glossary/#asic
[pow]: https://bitfalls.com/glossary/#pow
[steem]: https://steemit.com