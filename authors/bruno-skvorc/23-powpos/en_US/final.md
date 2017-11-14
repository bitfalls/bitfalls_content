Both in the glossary and in some of our previous posts we've touched on mining and the two main methods in use today: PoW and PoS. We'll discuss each method in this article, but first we'd like you to read the fundamentals: [intro to cryptocurrency][cc] and [intro to blockchain][bc] so that you can follow along nicely.

## Proof of Work

With Proof of Work, your miner (the computer or group of machines under your control) does the following:

- takes from the internet the order to process some transactions. In other words, it takes from the miners geographically closest to it a set of transactions it's supposed to verify, in which it is written who's sending how much of a [cryptocurrency][cc] to whom.

- the miner then builds a [block] - a list of transactions that need to be validated. How many transactions per block depends on the size of those transactions. Those which send from many addresses to many addresses are much larger than those sending money from one to maybe one or two addresses, as [previously explained][blockex].

- the miner combines all the data from this block (literally glues them together), adds some more data into the mix, and then tries to guess the final bit of data which will result in a valid [hash] when [hashed][algo]. For example, in Bitcoin, the hash has to be prepended by a certain number of zeroes. The computer, thus, does the following: "Try summing up all of this and the number 1. Incorrect? Okay, try summing up all of this and number 2. Incorrect? Okay, try..."

- the computer's processing power will dictate how many of such guesses per second it can do.

- after a successful guess, the computer gets a [block reward][bw] which is currently 12.5 BTC in Bitcoin, or 6.18 XMR in a system like Monero, etc.

The profits of mining this way will vary by hardware, software, and currency - we've gone into some detail [here][mining].

![A mining rig](https://bitfalls.com/wp-content/uploads/2017/10/02-2.jpg)

The advantages of PoW are:

- outside factor effect. With the PoW mechanism, the production and circulation of money requires external factors like power and hardware. It is not possible to get the expense of power or production of hardware back. Why this is important will be explained in the PoS section below.

- it's simple to [pool mine][mining]. It's easy to just grab another computer's calculated hashes, combine them into one big pool of hashes, and have many computers hashing together, splitting the profits.

- it's useful for areas with surplus electricity, like China with its hydroelectric dams.

The disadvantages of PoW are:

- PoW isn't possible on smaller and weaker devices like smartphones. Not only do these devices lack the space to store hundreds of gigabytes of blockchain data, but they're also not computationally powerful enough to mine effectively. The battery would be emptied very quickly, not really accomplishing anything.

- PoW mining is slow. With Bitcoin, it's one block every 10 minutes, and the transactions that fit inside that block will be processed. Anything else has to wait for the next block. This causes long waiting periods or expensive transactions (those that attach a higher transaction fee are processed faster).

- PoW is already spending enormous amounts of electricity. Simply mining a single block costs more electricity than some countries need in a whole year. This will only get worse. The dependence of a cryptocurrency on electricity is unsustainable in all but the most stable environments. This dependency also means that a more expensive electricity bill or a government-imposed limit to the types of spending electricity can be used for can [stop an entire cryptocurrency][unstoppable].

  ![Pollution](https://bitfalls.com/wp-content/uploads/2017/10/01-2.jpg)
  
- PoW allows for the centralization of mining. China already has 80% of the world's Bitcoin hashing power, and if their cartels join forces, we've got an 80% attack, not a [51% attack][51].

- Because the [block reward][bw] keeps decreasing, miners keep getting fewer and fewer tokens of a mined [blockchain][bc]. At the same time, as more people are mining, the mining [difficulty][bd] increases, so it gets harder and harder to mine. This makes mining more and more expensive compared to profits, and fewer people bother with it, exiting the system. The currency self-sabotages. Less hashpower among the miners also makes the [51% attack][51] more likely.

  As an example, Bitcoin might still rise to some $25000 or $50000 through the next 5 years or so, but as transactions get moved _off chain_ onto solutions like the Lightning Network (designed to transact small amounts on the side, without waiting for validation from the main chain, thus moving fees off the main chain too), mining becomes even less profitable. With block rewards approaching 0 and transaction fees all but gone, this will further escalate the miners' departure from the network, opening it up to a 51% attack or total stagnation.
  
  ## Proof of Stake (PoS)

![Dokaz uloga](https://bitfalls.com/wp-content/uploads/2017/10/03-3.png)

With Proof of Stake, no complex equations need to be guessed so powerful computers are no longer necessary, and with them, there's less need for electricity.

Examples of PoS coins: Ethereum (soon), BlackCoin, CoinMagi, Diamond, Mintcoin, OKCash, HyperStake, Quotient, etc.

Let's take Ethereum as an example. Proof of Stake works by randomly selecting a "validator" - an account with enough Ether to be considered a stakeholder, someone who's invested into the ecosystem. Initially, that would be 1000 Ether. The more Ether a validator has, and the longer it has been on the candidate's account, the more chance that they'll be picked. This validator then stakes the Ether (locks it up for a period of months) and guarantees to uphold the laws of the ecosystem - to truthfully validate transactions. Once a new transaction arrives, it's added to the block, validated, and the block is sent to the other validators for confirmation. For this work, the validator gets the transaction fees of the transactions they processed.

Because there's no more need to guess combinations and processing transactions is easy and cheap, it's easy to generate fake ones. But because validators have to reconfirm the information (like students in a school correcting each other's exam), it's almost impossible to think a bunch of validators will all confirm a malicious one's report. For this to happen, the malicious group has to not only be randomly selected at the same time (impossible), but also have 51% more Ether than the rest of the randomly selected validators who could have anywhere from the minimum to an astronomical amount of Ether.

Furthermore, if a validator is found to be malicious, they lose their stake and are kicked off the network. Cheating becomes an incredibly expensive sport. Someone with enough money invested into the Ethereum ecosystem to become a validator has no reason to sabotage this ecosystem because their holdings lose value (because of the scandal they caused if successful, or because they lose their stake if the cheating attempt fails).

The advantages of PoS are:

- speedy processing of transactions
- contrary to PoW, not harmful to the environment
- not vulnerable to a state attack: no need for enormous amounts of electricity
- can be performed on smaller and weaker devices because there's no need to download the whole blockchain, and since there's no need for much computational power either, can be easily adopted by the mainstream

The downsides of PoS are:

- no external factors. Given that the stake is a part of the system itself, the whole game is internal. This means that someone with enough money to invest exclusively into the destruction of this system can do so by investing only money, as opposed to Bitcoin where they need to invest money, time, expertise, hardware, electricity, and more - all external factors.

- the rich get richer. Those who have had their Ether the longest (the age of the Ether in an account is as much of a factor as the amount is) also have the best chances of becoming validators. This means their chances to earn more Ether on top of their existing pile also increases. This is different from Bitcoin's "rich get richer" system because there the rich have to keep investing in hardware and knowledge to remain competitive. It also hurts more to sabotage the network.

## Delegated Proof of Stake (dPoS)

![Glasovanje i politika](https://bitfalls.com/wp-content/uploads/2017/10/04-1.jpg)

In this PoS type, 101 delegates are picked by the community by voting with the cryptocurrency in question, e.g. 1 LISK 1 vote. Some blockchains have a different number than 101, but that's the default.

Delegates cannot modify transactions, only delay their inclusion into a block, but this has safety nets built into the protocol so prolonged exclusion of a transaction becomes expensive. This is also the only "technical" power these delegate validators have, and should they abuse the power, the community can instantly see it and vote them out.

Delegates get rewards for validating transactions, just like in PoS, so cheating again makes no sense because they lose both their stake and their role in the system. The rewards they do get they can spend on lobbying, spreading the word about the currency, cash it out into earnings, etc.

Some DPoS systems work in such a way that they can define a burn rate: a percentage of tokens to be destroyed upon getting a reward. For example, a burn rate of 40% will **destroy** 40% of the tokens received by a delegate. Destroying tokens leads to [deflation][finite], which leads to increased value of the remaining tokens - both those tokens in the hands of the delegates, but also the tokens in people's wallets around the world. It's like everyone who uses the currency gets dividends, because their money becomes more valuable automatically. The remaining 60% of tokens can, of course, still be used for anything the delegate wants to use them for.

Advantages of dPoS:

- a more even distribution of block rewards. People will elect only those delegates who give them the most rewards, so the causal users and not just big holders will be rewarded.

- real-time voting security. Any malicious action can be immediately detected by the voters and the malicious delegate can be voted out of the system.

- same as with PoS, it's very environment friendly and easy to execute on smaller and weaker devices. It's harder to stop because it doesn't depend on external factors controller by the state, like electricity.

Disadvantages of dPoS:

- it's possible that the delegates get organized into cartels. This already happened with the LISK blockchain which, even though it hasn't been released as a full product yet, has a cartelized dPoS in which 51 of the 101 delegates have joined and formed a "Lisk Elite Group" in which they vote for each other and don't distribute their gains to any casual user who hasn't voted for all of them. This is identical to the modern political system.

- because fewer people are in charge of keeping the network alive, it's easier to stop it or organize a [51% attack][51] (see above point about cartels).

DPoS is used by currencies like Bitshares, Crypti, Lisk, RISE, ARK, etc.

## Conclusion

There are other methods, too - like Proof of Importance in use by NEM (XEM). It's similar to PoS in that it values wallets with over 10000 XEM and calculates their importance score based on their holdings and their participation in the network - the more transactions are bound to an address, the more important it is as an active participant. But this too has obvious downsides.

None of the methods is perfect and each has its own set of problems keeping extremely smart people busy. When and how much progress we'll see remains to be seen but one thing is certain - the progress is coming, and it'll be the turning point at which cryptocurrency goes mainstream.

[51]: https://bitfalls.com/glossary/#51-attack
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
[mining]: https://bitfalls.com/2017/10/12/mining-investing-cryptocurrency-better/
[unstoppable]: https://bitfalls.com/2017/08/21/is-bitcoin-unstoppable/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/