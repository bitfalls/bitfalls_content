So you want to join Ethereum? How do you do that? Which wallet do you need? How do you set it up if you're not technical? Here's a breakdown.

Before diving into this, please read the [Ethereum introduction](https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/).

## Software and node types

Ethereum is a blockchain. This means that a software program known as a _node_ runs it and communicates to other nodes to make sure they all have the same data. These nodes are in turn based on different types of underlying software, the most popular two being Parity and Geth.

There are three main types of nodes: archive, full and light, so you have a flavor of Geth that's an archive node, and a flavor of Geth that's a full node, for example.

**An archive node** will build the whole blockchain from block 0, so from the beginning. It won't wait for blocks to build the regular way (i.e. 15s per block) but will instead check the data as fast as it can, exploring even the dead "forks" that never happened. This can take weeks, and will eat up more than 2 TB of hard drive space. It stores all the past states of Ethereum and lets you check balances and transactions for any wallet at any point in time. It gives you the full history of the blockchain. You cannot sync an archive node to 100% on an HDD, you must use an SSD. The HDD simply cannot spin fast enough. The good news is that you probably don't need an archive node (see use cases below).

**A full node** is similar - it also takes a long time to sync because it builds everything from scratch, but it keeps only the latest state and _proofs_ about past states. This is why a full node is only 80 to 130 GB, depending on who you ask, but you cannot query details about the past without rebuilding the blockchain up to that moment in the past. The good news is that a full node has the potential to be an archive node because it has all the data needed to build a full archive, it's just not "applied".

**A light node** is one that only reads a checkpoint in Ethereum's recent past, downloads the block headers from the blocks that happened since, and then makes sure the up to date state is true. It makes an assumption about the data that comes before - it implicitly trusts whichever node it used to grab that checkpoint. A light node can have trouble finding light node hosts to connect to as not many nodes run with light node slots open (it's an altruism thing).

Here's a thread of tweets that hopefully further clarifies things:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">A lot of talk about full vs archive nodes lately, along with an article of questionable quality from <a href="https://twitter.com/BlockCypher?ref_src=twsrc%5Etfw">@BlockCypher</a>. I would like to set the record straight with an example.<br><br>Assume X is the result of n! (n factorial).<br><br>X = 1 * 2 * (n-(n-3)) * ... * (n-3) * (n-2) * (n-1) * n</p>&mdash; Bruno Skvorc (@bitfalls) <a href="https://twitter.com/bitfalls/status/1105761796235907072?ref_src=twsrc%5Etfw">March 13, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">1. Light clients: ask full nodes about X. Get X, and some n&#39; where n&#39; &lt; n from which it is easy and fast to calculate X if you know you&#39;re dealing with a factorial.<br><br>2. Full nodes: have `n` and have `X`, and can at any time check that `X = n!`, knowing it&#39;s factorial.</p>&mdash; Bruno Skvorc (@bitfalls) <a href="https://twitter.com/bitfalls/status/1105761798630924288?ref_src=twsrc%5Etfw">March 13, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">3. Archive nodes:<br><br>These keep all the intermediary states. So those blocks at the beginning? Archive nodes store them. Key difference between full and archive?<br><br>Archive nodes know the answer to &quot;what was X at block 3&quot; - they know it&#39;s 6.<br>Full nodes need to recalculate from n = 1.</p>&mdash; Bruno Skvorc (@bitfalls) <a href="https://twitter.com/bitfalls/status/1105761799759151105?ref_src=twsrc%5Etfw">March 13, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">So, TL;DR:<br><br>- full nodes CAN BE archive nodes without downloading data from others<br>- archive nodes are useful only if you want quick access to past data, which is arguably better stored in other DB systems optimized for your type of query<br>- the network does not NEED archive nodes</p>&mdash; Bruno Skvorc (@bitfalls) <a href="https://twitter.com/bitfalls/status/1105761800983846912?ref_src=twsrc%5Etfw">March 13, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

For more descriptions and commands on how to run these modes, please see [Running an Ethereum Node](https://docs.ethhub.io/using-ethereum/running-an-ethereum-node/).

So... what's a wallet?

The _nodes_ mentioned above can be considered "back ends" - servers, basically, but server programs you run on your computer. They are **not wallets**. However, they can become wallets if you import a wallet into them. You use user-interfaces like Mist (now [discontinued](https://medium.com/@avsa/sunsetting-mist-da21c8e943d2) so please don't use it), [MetaMask](https://bitfalls.com/2018/02/16/metamask-send-receive-ether/), [MyCrypto](https://mycrypto.com), [MyEtherWallet](https://myetherwallet.com) or some of those mentioned at [Wallets.Review](https://wallets.review) to connect to these nodes, and then those nodes talk to the blockchain for you - sign transactions and read balance - and send that info to the user interface app for you to see.

So when do you need which tool? How hard is it all to set up?

## Mining

We have to note that none of the aforementioned nodes is a _miner_ - to mine cryptocurrency you need expensive hardware like lots of graphics cards or specialized hardware called ASIC. The program that's doing the mining using this hardware sends its guesses to one of the aforementioned nodes, if such a node was run with the "mining" flag turned on. Mining is outside the scope of this article.

## Joining just to have a wallet

If you just want to have a wallet, all you need is a private / public keypair. If you want to know more about this crytography stuff that's powering cryptocurrency, we have a very good newbie-friendly introduction [here](https://bitfalls.com/2017/11/16/cryptography-mortals-lets-explain-public-private-keys/). You can generate this with any wallet, but the easiest way is to open up something like [MetaMask](https://bitfalls.com/2018/02/16/metamask-send-receive-ether/), [MyCrypto](https://mycrypto.com), [MyEtherWallet](https://myetherwallet.com) and generate a wallet. This will result in the creation of a password-encrypted keystore file (a text file ending in `.json`) which you can print or save somewhere safe.

Any wallet software can use this file to sign transactions from you and once you send such a transaction _into the ether_, be that via MetaMask, Mist, pigeons or smoke signals, the transaction (tx) gets executed. Likewise, merely having the public key of your wallet (looks like `0x4522bc91fd54982938...`) allows you to accept Ether and tokens and you can check your balance at any time without inputting your private key anywhere. Remember - if you lose  your private key, you lost your money. If someone steals your private key, they have your money. Hide it and use it ONLY when sending transactions, on your own internet connection, on a safe browser clean from extensions.

Alternatively, use a [hardware wallet like a Ledger Nano X](https://www.ledger.com/?r=7410) which takes care of most of this for you by keeping the private key on its secure chip. Additionally, the hardware wallet comes with its own application serving as your wallet, so you're up and running as soon as you open the box.

Recommended approach for a wallet:

- For daily amounts for use around the web (up to $50), use the [MetaMask extension](https://metamask.io).
- For long-term holding of cryptocurrency, use a [hardware wallet like a Ledger Nano S or X](https://www.ledger.com/?r=7410) or print the keystore file on a piece of paper or, better yet, engrave it in metal, and hide it in a safe place.

It is **absolutely not recommended** to hold cryptocurrency on an exchange, as an exchange can simply disappear overnight as we've seen countless times, no matter how big it is. There is no "too big to fail" in cryptocurrency.

"But how secure is it if I'm using a website for my wallet?" you might be wondering. As long as your private key is in your possession, it's secure. The website is just providing a user interface through which to interact with the blockchain using your private key, but most of these projects are open source and you can run them offline. Here's a slightly outdated tutorial on using MyEtherWallet on your own computer, without running their website: [Running your own MyEtherWallet](https://bitfalls.com/2018/04/24/how-to-run-your-own-copy-of-myetherwallet-for-maximum-security/).

## Joining as a User

This is the same as above, though I would recommend checking out some [mobile wallets as well](https://wallets.review). There's quite a lot to do on mobile in web3 these days, so some of these apps are definitely worth checking out.

Apart from this, when you really want to join as a user who is connecting to their own node for whatever reason, each of the tools mentioned above has a "Custom network" functionality which lets you add a custom IP address and port of the node you want to connect to. So if you're running your own node, which is [cheap and easy](https://blockandmortar.io), you can connect to it by selecting custom node and entering your node's IP and port.

Advantages of running your own node are:

- you help the network by diversifying it
- you get an indisputable source of truth in that you can check the blockchain data yourself, you don't trust others to do it for you
- you help light clients (light nodes) connect if you run a node with light client slots. That's purely good karma there, but can also be monetized with approaches like [VipNode](https://vipnode.org/).

## Connecting to my Private Blockchain

If you have a private blockchain running on a remote node, you can connect a wallet UI like MetaMask, MyEtherWallet, or MyCrypto to it via RPC (Remote Procedure Call). Depending on the software you're using to run the private chain's node, you'll have to start it with some extra options: open RPC and specify port. Additionally, you might have to open that port in your firewall and/or router, depending on where you're running the node. 

For best results, run a node locally on the same network you're connecting from - they are [very cheap to run](https://blockandmortar.io). As an example, see [Lisinski](https://lisinski.online/en), a Croatian testnet where the nodes are running on everything from AWS to custom micro-nodes like those from Block and Mortar linked above, in different offices around the country and outside it.

More details on how to connect to a private blockchain available [here](https://bitfalls.com/2018/03/26/connecting-myetherwallet-mist-metamask-private-blockchain/).

## Joining as a Developer

Your best bet is starting with something like [Truffle](https://truffleframework.com) or [Embark](https://embark.status.im). Both frameworks have extensive documentation that wonderfully explains things, and both will have active social media channels via which to seek help.

If you'd like to query data faster without relying on someone else like Infura (a big, centralized Ethereum data provider everyone seems to be relying on), run your own node - it's very cheap to start with and almost free to run. Get them on [Block and Mortar](https://blockandmortar.io).

Additional advantages of running your own node are:

- you help the network by diversifying it
- you get an indisputable source of truth in that you can check the blockchain data yourself, you don't trust others to do it for you
- you help light clients (light nodes) connect if you run a node with light client slots. That's purely good karma there, but can also be monetized with approaches like [VipNode](https://vipnode.org/).

## Joining as an Investor

First make sure you "Join as a User", then:

- if you invested [via an exchange](https://www.binance.com/?ref=10883771), put your money in cold storage (printed or engraved wallet) / hardware wallet
- if you're not investing via an exchange (i.e. [Binance](https://www.binance.com/?ref=10883771)), then use a brokerage which can send Ether directly to your address like [Coinvendor.io](https://coinvendor.io).
- use view-only apps to monitor your assets. Examples include [EthView](https://ethview.app) and [Etherscan.io](https://etherscan.io)

## Ethereum 2.0 and proof of stake

Ethereum 2.0 is a long ways off. Maybe keep an eye on the [Ethereum 2.0 series](https://our.status.im/tag/two-point-oh/) or on [Ethhub](https://ethhub.io). For the difference between Proof of Work and Proof of Stake, see [here](https://bitfalls.com/2018/04/24/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/).

---

If anything is unclear, please let me know [on Twitter](https://twitter.com/bitfalls) or submit an issue in our [content repository](https://github.com/bitfalls/bitfalls_content).