The [Novathon] hackathon took place on the 23rd and 24th of September in Zagreb Croatia. It was a fintech oriented hackathon sponsored by PBZ (the local branch of the Intessa bank group) and the aim was (at least on paper) to create new financial technologies that help users take control of their finances and regain financial freedom.

Naturally, our team - Bitfalls - approached the problem from a cryptocurrency angle.

## Idea: Government-backed Cryptocurrency

Given that banks are "afraid" of [cryptocurrencies][cc] due to their decentralized nature and the freedom from the financial system they provide citizens with, it's probable that the most corrupt and greedy governments will be pushing cryptocurrencies in general into [illegality][unstoppable].

This "war on crypto" would be just as effective as the war on drugs. Everyone who's already "on crypto" would continue using it in _the underground_. The whole crypto ecosystem would become even more rife with scams and frauds due to lack of regulation and the absence of big state players, [crypto cartels][gold] whose only goal is profit would show up, and the people who would get hurt the most would be the casual, "recreational" users, while the government would lose a big part of the pie. The potential for tax gains and bank earnings in crypto is immense, as you'll see below.

So why not combine these two worlds? Why not connect the corporate, banking sector and the government sector with the new, revolutionary world of [blockchain][bc] technology, while at the same time making it possible for civilians to have a safe and smooth entry into the crypto world, simultaneously dramatically improving the banking system as a whole?

## dKuna

![Dkuna logo](https://bitfalls.com/wp-content/uploads/2017/10/01-6.png)

Our idea was a cryptocurrency called "dKuna" or "digital kuna". Kuna (HRK) is the national currency of Croatia, named after a [local rabid weasel of some kind](https://www.google.com/search?q=musteline&oq=musteline&aqs=chrome..69i57j0l5.1552j0j7&sourceid=chrome&ie=UTF-8), and the name of the cryptocurrency can be anything - KunaCoin, HRKoin, doesn't matter. The concept is also applicable to any other centralized fiat currency - we picked Kuna because of the locale in which the hackathon was happening. It could just as well have been a Euro, Yen, or something else.

The dKuna is an [ERC20 token][eth], which means it's built with a _smart contract_, a small program on the Ethereum platform. Seeing as we're talking about a cryptocurrency on the public blockchain, all transactions are [anonymous][anon] but public and easy to read with some [dedicated tools][blockex].

The idea was as follows:

- the smart contract which controls the currency's supply has the ability to mint new ones and to destroy those that get sent in.

- HNB (Croatian national bank) which owns this contract would thus have the ability to create new tokens. This would happen when a deposit is made. For example, if company X deposits 30k HRK in fiat, HNB will use the smart contract to mint 30k dKuna and send them to company X. If company X sends back 15k dKuna after a while, 15000 dKuna tokens get destroyed (_burned_) by the smart contract, and 15k of the HRK deposit is released back to company X. This makes wild inflation impossible because the ratio of dKuna and fiat HRK is kept balanced, and because the creation of new dKuna is transparent and visible on the blockchain.

- the contract which can mint and burn tokens can be controlled by several parties, but controlling it requires a certain number of private keys. For example, five of the ten authorized people in HNB need to authorize a transaction - like a "create new tokens" transaction - for it to be valid. We can compare this setup with a vault which needs two people to turn their keys at the same time to unlock the door. Furthermore, supervising agencies have their own sets of keys to this contract, but they might need seven of the top ten people in their organization to authorize something like a takeover. Interpol can have its own keys and its own ratio of required vs. total, etc. The more agencies have access to the dKuna logic, the smaller the chance of corruption.

- the contract has an ownership transfer function. In case some keys get leaked or lost, the security of the entire contract can be reset back to its impenetrable state by simply changing the owner to a new set of keys of which 50% are needed to control the contract. This can happen in minutes - no other system in the world is as safe as this one. This functionality is also useful in case a government starts to turn on its people - either economically or otherwise (see Venezuela, India, Zimbabwe). At that point, a supervising union like the EU, UN, or another group can take control of the dKuna system and put a stop to the chaos.

_It's important to note that our implementation at the hackathon did not stop at the idea level. We had a fully functioning dKuna system up and running in those 24 hours, and we even tested it by sending dKunas around to each other._

### Possible Use Cases

**The primary goal of dKuna was as follows:**

- security and global compatibility
- total removal of corruption from public service and transparency towards citizens
- complete automation of financial bureaucracy
- painless entry of citizens into the crypto world, and entry of local currency into the global market

Let's take a look at each in a bit more detail.

#### Security and Global Compatibility

![Illustration of a thief hacking a computer](https://bitfalls.com/wp-content/uploads/2017/10/02-4.jpg)

Since dKuna is an ERC20 token, it can be sent to any Ethereum address. You can save your dKuna onto your [hardware wallet][ledger], onto your cellphone, on your computer, or on a [piece of paper][paper]. You can send them across the globe in an instant without the recipient having to have an account in a compatible bank. No three-day wait for SWIFT, no commission. Not only that, but they're also trivial to send from bank to bank without going to the actual bank. Using a simple [Ledger][ledger] device or a wallet like [MyEtherWallet][mew] makes it possible for you to send dKuna to any bank which accepted the dKuna system - in Croatia's case, that would be all the banks, if HNB decided to adopt it.

Banks could very easily implement this new system, so the features can become accessible in regular netbanking apps almost immediately. Remember - we're dealing with a public blockchain which is globally secured. We're talking about an infrastructure which already exists and is nearly indestructible. The capital and time needed to add this into existing systems are miniscule.

It's worth noting that while it may seem odd to be giving five people full control over a country's financial backbone, the current system has an even bigger single-point-failure chance. A single admin or programmer who hadn't had enough sleep last night can, on his own and with the mere misclick of a mouse button, throw the entire system into chaos. With Ethereum and smart contracts this isn't possible because once the program is on the blockchain, it's secured and verified by thousands of people across the globe. The only time when bugs can appear is during development, and if the smart contract is ironed out to perfection at that time, once it's deployed it becomes indestructible and unhackable.

#### Total Removal of Corruption

Because of the [anonymous][anon] but public nature of the blockchain, all transactions are visible - including both the ones purely monetary in nature, and those used to create new dKuna tokens or burn them. Just grabbing a bag of cash and running off with it is no longer a possibility, because dKunas wouldn't be spendable without transactions showing up on the blockchain.

The public nature of the blockchain also automates the auditing of HNB's fiat reserves. Since it's easy to find out how many dKuna are in circulation at any given moment, the auditing agency in charge of making sure there's enough fiat in HNB's coffers knows exactly what to look for. If the amount in deposit doesn't match the number of dKuna **exactly**, someone is doing something wrong. And since every transaction is signed with a key, it's easy to identify which part executed the invalid transaction which resulted in a discrepancy.

Unnoticed multi-billion-kuna loans also become impossible to execute, and society in general can't spend more money than it has. Uncontrolled inflation also becomes impossible (we currently have no way of knowing how often and how much of a currency is released into circulation).

#### Total Automation of Financial Bureaucracy

![A robot drawing itself drawing itself drawing itself](https://bitfalls.com/wp-content/uploads/2017/10/03-5.jpg)

dKuna makes the fiscal system, a draconic system making things difficult for small businesses in Croatia due to excessive manual tracking, obsolete. Because all transactions are saved on the blockchain, if company X with its 30000 dKuna identifies itself with the IRS as the owner of address XYZ, the IRS gains the ability to not only audit all transactions ever made automatically, but also to calculate profits, losses, and tax obligations of each participant of this system without the need for any third party bookkeeping or accounting services.

_Biljezi_ - little stamps we have here that serve as proof you paid some money into the public system, often used during the issuance of new government IDs like passports - become obsolete, too, because the transaction is mathematically provable forever without a need for a receipt. You simply give them the transaction ID, and all the proof they might ever need to verify it is right there. Queueing in general goes down dramatically because the software required to use the Ethereum blockchain is publicly available - whether it's via a Ledger device, through MyEtherWallet, or with a mobile app, dKunas are easy to send to anyone at any time and become visible and mathematically unfalsifiable almost instantly. In general, all need for receipts disappears.

Granted, this means a lot of people would lose their jobs. IRS inspectors, finance control, middlemen, tellers, auditors, even accountants in some cases. Everything would be automated. Why spend human resources on something so superficial when it's 100% automatable to infallibility, and when those same people could instead be educated to [keep an eye on the blockchain][blockex] and see if they can spot any fishy transactions or attempts at corruption?

#### The Crypto Market = The Global Market

Because of the ERC20 standard and the ability to send dKuna to any international Ethereum address or exchange, a whole new world of financial opportunity becomes available to the average citizen. From [investing in other cryptocurrencies][folio] to easy and transparent access to [web shops][shop], the crypto-globalization of the Kuna would pop the isolated bubble Croatia has been in for so long, and push the country into the global market for real.

But... why would the banks sign off on this? Why free their clients this way and give up their fees?

Even if we ignore the fact that this is going to happen eventually and that citizens will run from the banking system regardless, the banks can benefit by jumping on board early due to the following added services and features:

- investment funds based on cryptocurrencies already exist, but are lead by non-banking private companies. Just look at the Croatian [Digital Assets Power Play](https://www.dapowerplay.com/) or projects like [ICONOMI](http://iconomi.net), [Melonport](https://melonport.com/), [Prism](https://info.shapeshift.io/blog/tags/prism) and others. The commissions banks can collect here are immense, and surpass the GDP of some countries already - purely because of the global reach of this technology.
- saving with crypto becomes an option - whether you're saving in dKuna or in an inflation-resistant cryptocurrency.
- commissions earned on exchanging currencies are another profit option for banks.
- loans when they're based on crypto become a little more moral and a little safer - backed by the entire blockchain, conditions of a smart contract can self-execute when the time is right or when some triggers happen, like a client paying off a part of the loan, and the contract auto-adjusting interest rates and payout dates. This is different than a bank's internal system because it's global, transparent, automatic, and inspectable by all. It's fair.

![Iconomi](https://bitfalls.com/wp-content/uploads/2017/10/04-5.png)
_ICONOMI investment fund graph_

Banks can also issue debit cards from which users could spend cryptocurrency. Since the dKuna is an ERC20 token, any address accepting dKuna can also accept any other crypto token based on the ERC20 standard. So for example, if a client stored some [OMG](http://omg.omise.co) currency on the same address, the debit card could be made to spend that when the user chooses it, or switch to dKuna. This brings cryptocurrency into the mainstream, and lets banks earn commissions on debit card payments and conversion rates - just like they do now when you use a debit card that holds currency A in a store which operates in currency B. These options already exist, but are mainly privatized and non-banked. See [TenX][tenx], [Bitwalla], [Monaco], etc. Notice that each of these is VISA-based. VISA know what they're doing, and they seem to be keenly aware of which market needs penetrating.

Looking at cryptocurrency with a purely critical eye and ignoring not only the tech advancement but also the earning potential is nothing short of ludicrous.

## Similar Solutions

You may have heard of USDT or USD Tether: a similar cryptocurrency which operates at a 1 USDT = 1 USD ratio. USDT are minted by a single company, Tether.io, which has no audits or banking licenses. Moreover, most banks have exiled them and refuse to do business with them. Regardless, USDTs are still being created out of thin air, and used on the Bitfinex exchange to buy Bitcoin. We're talking about a large criminal organization which lies to its users and uses its non-existent cryptocurrency to pump Bitcoin's value.

![Pumpanje cijene bitcoina](https://bitfalls.com/wp-content/uploads/2017/10/06-1.jpeg)

For more on this, please see [this post][tether] or attend the [F2] conference.

dKuna is different in that it's transparent to all citizens, but centrally regulated and controlled by a government institution. Oversight is given to further, more powerful organizations, going up as many levels as necessary to make corruption non-viable. To turn such a complex machine into a corrupt one, the whole world would need to be absolutely criminal - not just governments and the super-governments above them (e.g. EU), but also the world's auditing agencies, international police, media, etc. Even if this should happen and the whole world turned evil, it would be immediately apparent because the whole state of the blockchain is readable to everyone at all times. The public would notice and rebel.

Apart from the aforementioned Tethers, since Novathon ended two more "government sanctioned" currencies appeared on the horizon:

- Russia is [planning to make][cryptoruble] a cryptoruble. It'll be possible to exchange them 1:1 like with dKuna, and if the owner of cryptorubles can't explain its origins, they'll have to pay 13% tax. This prevents efficient money laundering but doesn't fully stop cryptocurrency trading in the country. It seems unlikely that the state will force the ratio to remain at 1:1 because they added an extra clause stating that any earnings made on the difference in value between purchase and sell price are also subject to 13% tax gains, like capital gains tax. For example, if someone changes 1 ruble for 1 cryptoruble on Jan 1st 2018, and then the cryptoruble is for some reason worth 10 rubles on Jan 1st 2019, the 13% tax applies to the 9 ruble gain at the time of the sale of the cryptoruble. There's no anti-inflation deposit measure in place, but they might add it later.
- Dubai will soon issue [emCash]. This currency isn't bound to a local one in any fixed ratio, but is government sanctioned and supported for everyday trade.

In spite of these countries waving their blockchain feathers around, I personally believe Sweden will be the first country to surprise us all with a government cryptocurrency. In fact, I believe it'll be almost identical to how the dKuna works or was intended to work.

They're already a cashless society - countless stores have "plastic is fantastic" and "no cash" signs, and even hot dogs in the street are paid with credit and debit cards. Cash is so far outside their system already, there are stores and shops that downright reject it. Given their focus on transparency (every expenditure of a public official is visible to everyone and available for inspection not only to citizens but also to media), I believe they'll be the first country to fully transition to this system of auto-auditing and full transparency.

Many wonder "Why would they, if their current system works?". The answer is: because when dealing with a currency that's on a global public blockchain, exiting the system is easy if the government corruption gets so bad the state turns against its own people and starts to take over bank accounts (which, in a centralized system, is easy) or starts printing [trillion dollar bills][zim].

![100 trillion dollar bill from Zimbabwe](https://bitfalls.com/wp-content/uploads/2017/10/05.jpg)

It's the same reason why Americans to staunchly refuse to give up their weapons (at least on paper). Their constitution says that they have the right to bear arms for the purpose of (among other things) mobilization against a tyrannical government.

Swedes value their freedom, and freedom from corruption is absolutely paramount.

### Private blockchains

We've been asked several times now why a state or a bank wouldn't instead make a private copy of the Ethereum blockchain and just spin up its own cryptocurrency that way. That way transactions become private and everything is under the control of that one entity, without depending on a global system of users. Incompatibility with the global Ethereum blockchain and its ERC20 standard aside, this approach has zero advantages, and two major disadvantages:

1. A private blockchain removes transparency and does not improve the public's trust towards the government or banks using such a system. If the state or bank are hiding something, it's assumed they have something to hide.
2. With private blockchains, the entity that's setting it up must also spin its own nodes to verify transactions. The blockchain is very slow in writing data: a transaction needs to get signed, sent, verified, and confirmed once it's in a [block] that needs to get mined. If an institution replaces its own servers with blockchain nodes, all they did was replace their fast database with a new, slow one. If a fire or a flood happens in their datacenter, they still lose everything. There is no advantage in having a private blockchain if you're not transparency-focused. Use a regular database, it's the better option.
 
## Conclusion

Admittedly, our 24-hour idea has some holes that need plugging and some parts that need more thinking devoted to them, but its purpose was to show the banks and the jury how easy and cheap it is to implement cryptocurrencies into the existing system - without wars or conflicts of interest. Centralization isn't always bad, and decentralization isn't always good. [Deflation and inflation][finite] each have its own pros and cons. Not everything in the world is polar, and to dramatically improve a given system that system has to adopt what's good from another system and discard what's bad or incompatible with the first system's idea.

A common complaint from the corporate sector when talking about dKuna was about giving users too much freedom, thus opening the door towards money laundering, tax evasion, and similar white collar crime. But corporate and state players keep forgetting that [even detergent][tide] can be currency if needed. Criminals will *always* find a way to move the goods they need to move - bans and strict regulations benefit no one because they remove the legal, casual users from the system. And the system is based on those casual users. These users are the users who need this freedom the most, because without it they continue to not have faith in the government, democracy, or the banking system.

Based on the cryptocurrency resistance we've encountered so far in Croatia, we're assuming this country won't be joining this new wave of technology for the foreseeable future - maybe 5 to 10 years. But we're [not giving up on education][blockconf] yet. Maybe we'll succeed in bringing the country into the 21st century and, for a change, make it a market leader rather than a limping, left-behind follower.

[unstoppable]: https://bitfalls.com/2017/08/21/is-bitcoin-unstoppable/
[gold]: https://bitfalls.com/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[tether]: https://bitfalls.com/2017/10/21/the-curious-tale-of-tethers/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[anon]: https://bitfalls.com/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[blockex]: https://bitfalls.com/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[ledger]: https://bitfalls.com/shop/ledger-nano-s-bitfalls-3/
[novathon]: http://novathon.net
[mew]: https://MyEtherWallet.com
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[tide]: http://nymag.com/news/features/tide-detergent-drugs-2013-1/
[blockconf]: http://blockconf.io
[folio]: https://bitfalls.com/portfolio-management/
[cryptoruble]: https://cointelegraph.com/news/breaking-russia-issuing-cryptoruble
[emcash]: https://www.cryptocoinsnews.com/emcash-dubais-first-official-state-cryptocurrency/
[zim]: http://edition.cnn.com/2016/05/06/africa/zimbabwe-trillion-dollar-note/index.html
[block]: https://bitfalls.com/glossary/#block
[tenx]: https://www.tenx.tech/
[Bitwalla]: https://www.bitwala.com/
[f2]: http://f2.bug.hr
[monaco]: https://mona.co/
[paper]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[shop]: https://bitfalls.com/shop/ledger-nano-s-bitfalls-3/