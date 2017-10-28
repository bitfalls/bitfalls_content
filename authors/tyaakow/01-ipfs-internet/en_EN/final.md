_Disclaimer: The following theoretical technical introduction is, while useful to everyone, meant for an intermediate IT audience and might be a little too technical for the casual reader._

---

When it started, the internet was a huge promise of decentralization and democratization of knowledge and information, both in the consuming and in the publishing sense. Before internet, one had to have a newspaper or a broadcaster - or a book publishing company under their control to get their message across to the general public. The same goes for music and videos. 

Publishing your own music and video work and putting it before the eyes and ears of a global audience meant that you had to have a lot of resources.

The internet changed this. 

## The Internet's Structure

Today, if one has quality content and a tiny bit of technical expertise (or a modest investment), they can make their content accessible to anyone  across the globe with internet access.

Information has been democratized. Knowledge is widely available today, so is publishing. Anonymous leakers of classified political information can expect to influence the outcome of the elections, regardless of whether the mainstream media had been bought and is owned by any of the parties. There is much greater liquidity of information than ever before in history.

We can say that the internet has changed things for our civilization as much as Gutenberg's invention has.

But things are not as bright as they seem. With mass internet adoption came big money, and with big money came monopolies and the centralization of users' data, and of control of information.

This is largely a centralization by convenience, not by compulsion. For this, we have the current internet structure to thank. We can find fault in the http protocol, client-server architecture, DNS - IP based routing and content addressing.

***This image shows one of the first web servers,by Tim Berners-Lee, with a note: This machine is a server. Do not power down!!***

![web server, T. Berners Lee](https://bitfalls.com/wp-content/uploads/2017/10/01-4.jpg)

The internet has strayed. The Turkish government has blocked access to Wikipedia in April 2017 because Wikipedia wouldn't take down an article that claimed that Turkey was sponsoring Al Qaeda and ISIL. The ban is still active. The government of China has blocked around one fifth of the world's population from accessing websites like BBC, YouTube, Facebook, Twitter, Amnesty International and many, many others. It's using what's called "The Great Firewall of China". 

2016 and 2017 saw huge internet outages due to the DDOS attacks and data-center errors that brought big parts of the internet down.  These events showed us just how much we depend on single vendors like Amazon AWS, CDNs, DNS providers...

We rely on content stored in particular data centers in certain countries, behind specific internet backbones. These outages were possible due to the structure of the network. 

![Wikipedia Turkey logo](https://bitfalls.com/wp-content/uploads/2017/10/02-5.png)

Not to mention the censorship, server seizures, and similar obstacles.

Our centralized model of data storage, which has been mitigated to a very small degree by CDN providers, is to blame for big wastes in bandwidth, and big losses in speed due to latency. If our source data center is geographically too far, we will see significant decreases in loading time and throughput speed of our connection.

### We are dependent on network backbones

If we are accessing a website hosted on a server on another continent, we are relying on one - or perhaps several - internet backbones for access to our website, because the content is stored centrally. Certain big internet players have redundant data centers across the globe, but this merely proves the point that the internet has strayed from its mission.

### We are dependent on internet hosts

Our content is stored on servers by hosting and server companies (cloud hosts are merely clouding this fact). If the servers of the hosting company in question go down - our content is also down. Moreover, if your host decides to take down your content - they can do that.

### Our content is easy prey

Under the current model, our content / resources / information / knowledge is inherently censorable, extinguishable, and corruptible. Hackers alter and deface websites so often, it is hardly news anymore. Government censorship is also something we meet every day. [Archive.org](http://web.archive.org/) has built a kind of an internet museum for previous years of the internet, but we need an internet more resilient to all sorts of decay.

![Burning of Alexandria, by Hermann Goll, 1876](https://bitfalls.com/wp-content/uploads/2017/10/03-4.jpg)

We shouldn't allow a single (or several) points of failure for access to the internet, especially because it's become a compendium of human knowledge.

At this point, the internet is conceptually broken.

## In comes the IPFS

IPFS, or Inter Planetary File System, is an open-source project by [Protocol Labs](https://protocol.ai/) started in 2014 by Juan Benet. The IPFS concept is very innovative. Maybe the closest thing we had before it came along was [Freenet](https://freenetproject.org/),  or Bittorent. IPFS is working to reinvent the internet **on the protocol level**.

It combines the technological advancements of Bittorrent, Git, cryptographic hashing, merkle trees, Kademlia DHT, etc. and it's aiming to thoroughly redefine how we do things online. 

### IPFS decentralizes storage

Any computer on the network can be a server. Storage is decentralized and distributed. Since things / content are not addressed by IPs, there is no inherent need for static IP addresses. This eliminates the need for dedicated data centers, and reliance on hosting providers.

### It uses content-addressing

This means that content is addressed by its [cryptographic hash](https://bitfalls.com/glossary/#hash). A piece of content is named by its content, not by the location of its server. If we compare our strayed internet model to addressing a book by the physical address of a library and the number of the shelf the book is on, IPFS goes back to naming / addressing a book by its title.

Content-addressing (by way of hashes) ensures data integrity, because if even one letter in any stored file changes, the hash is completely different. This opens up the possibility of versioning content similar to git commits. Reverting, transparency, and immutability are all available with this model.

Content-addressing means that we can have CDN-level distribution and efficacy of fetching content, because content can be distributed on hundreds or thousands of nodes all over the internet in a redundant way. This ensures we can still easily require the same content regardless of where we are fetching it from - even if half the internet is down. In this system, circumventing things like the Turkish Wikipedia censorship becomes child's play. Users can easily require same content from their local "swarm" of nodes inside Turkey. Any node on the IPFS network, once it retrieves the content (like a website for viewing), can cache it and become a trustable source of the same content.

In the existing internet model, if a piece of content is moved somewhere else, all links to it need to be updated.

Content-addressing means that the same content - hosted anywhere, or moved anywhere - is still accessible under the same address. The ***HOW*** part is up to the protocol.

(*Disclaimer - we shouldn't mix data **permanence** and data integrity or consistent addressing of content with **persistence**. The [ipfs-cluster](https://github.com/ipfs/ipfs-cluster) - currently in alpha, with a very active development, will be in charge of persisting or **pinning** of content across multiple nodes*)

### IPFS employs Kademlia DHT  (among other things)

IPFS uses a Bittorrent-like algorithm of *[Distributed Hash Tables](https://www.wikiwand.com/en/Distributed_hash_table)* - ***DHT*** - that doesn't require a central authority for reaching certain content. The Kademlia algorithm allows for any content lookup to take a maximum of `O(log(n))` hops / contacts for `n` number of nodes on the network. This is like a  maximum of 30 hops/lookups for 1,000,000,000 nodes. It is fast. It also means **no single point of failure**, **DDOS resistance** and **speed**. If our neighbor next door has some content cached / stored on his machine, we won't need to fetch it from across the planet. And we won't need to worry about data integrity.

Currently, as Juan Benet explained in [his Stanford presentation](https://www.youtube.com/watch?v=HUVmypx9HGI), the main work behind IPFS is not the protocol itself and its algorithms, but rather the integration of it into the existing ecosystem. For example, there is work to include IPFS content-based addressing and its protocol layer into existing browsers. 

There is work to integrate IPFS with local file systems via [FUSE interface](https://en.wikipedia.org/wiki/Filesystem_in_Userspace) (so we won't need to use the http protocol layer to access content). The majority of work is in integrating the new system into the existing one, seamlessly for end-users.

### IPFS is protocol-agnostic

One of the appealing features of IPFS is its protocol versatility. It can use TCP, UDT, Tor, or Bluetooth for communication.

Coupled with its DHT lookup scheme, this allows for development of applications that are immune to censorship attempts and able to "flow" under the radar. The implications of these two components (decentralized architecture and protocol versatility) are big.

### IPFS improves and builds upon protocols and apps that already exist

Bittorrent itself is a huge technological thing. It has avoided censorship and proved resistant to shutdown attempts. Its decentralized nature doesn't lend itself easily to crackdowns. IPFS is building on the shoulders of giants here. The difference is - IPFS has a thoroughly different focus. 

For example - with Bittorrent, content is packaged and we download those packages in chunks. IPFS, being a file-system, uses block-level addressing / deduplication of content, which is much more atomic, and allows for [big bandwidth savings](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6).

Also, while Bittorrent requires a separate layer for metadata / trackers, IPFS aims to solve all of this, and more. We could say that IPFS is casting a wider net, and providing a more elaborate package of solutions.

To quote the IPFS whitepaper, 

> *Unlike BitTorrent, BitSwap is not limited to the blocks in one torrent. BitSwap operates as a persistent marketplace where nodes can acquire the blocks they need, regardless of what files those blocks are part of. The blocks could come from completely unrelated files in the filesystem. Nodes come together to barter in the marketplace*

This means a much more efficient internet. For example, if my neighbor has previously loaded some content and has it cached on his system, I could be loading 40% (or more) of the required web page / content - not from a remote datacenter, or even from a CDN, but literally from a house next door.

**[Bitswap](https://github.com/ipfs/go-ipfs/tree/master/exchange/bitswap)** is an IPFS module in charge of these bartering / marketplace mechanisms, and it has on its roadmap opt-in or easy-opt-out possibility of caching content for others. By default, the content we do not request directly as a node isn't cached.

According to [IPFS faq](https://github.com/ipfs/faq/issues/47), 

> *...by default IPFS will not download anything your node doesn't explicitly ask for ... protocols layered on top that may download content for the network, but these are optional and built on top of basic IPFS. Examples include bitswap agents, [ipfs-cluster](https://github.com/ipfs/ipfs-cluster), and [Filecoin](http://filecoin.io/).*

### IPFS allows cloud-computing as it was imagined

This means resilient, redundant, reachable on demand content with the promise of high availability and low latency. An offshoot of the project is [libp2p](https://libp2p.io/) - an MIT-licensed set of libraries for swarm-based, p2p computing.

It is still a work in progress, albeit highly promising. And it is not a purely theoretical mishmash. 

From August to September this year, the [largest ICO so far took place](https://www.coindesk.com/257-million-filecoin-breaks-time-record-ico-funding/), raising a record-breaking $260,000,000. It was the Filecoin ICO for an application leveraging IPFS infrastructure, by Protocol Labs. To clear things up, the 260 million was not all ICO-raised, uninformed money. [52 million were raised in a presale from VCs](https://www.coindesk.com/filecoin-presale-raises-52-million-ahead-ico-launch/) who - presumably - knew what they were getting themselves into.

So the project might be onto something.

![OpenBazaar repos on github](https://bitfalls.com/wp-content/uploads/2017/10/04-3.jpg)

One more working product built on top of IPFS is [OpenBazaar](https://www.openbazaar.org/). OpenBazaar is a pioneer as far as the future of the internet and the internet's decentralization is concerned. It is a revolutionary p2p market which is well out of its idea stage (it is version 2.0 at the time of this writing). It works, and it works well. And it uses IPFS for storage.

One more working product which is implementing IPFS is [Steemit](https://steemit.com) - which plans to use IPFS for storage.

[Digix](https://digix.global/) is another [blockchain](https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/)-based startup / token with a market cap of $130 million at the time of this writing. It builds on IPFS, among other things.

[Mediachain](http://www.mediachain.io/) is another blockchain-based project using IPFS.

Then there is Orbit - a distributed, peer-to-peer chat application built on top of IPFS, giving birth to a new app layer on top of it - [orbit-db](https://github.com/orbitdb/orbit-db) - a "distributed peer-to-peer database for the decentralized web". You can check out Orbit [here](https://orbit.chat/#/connect).

The list goes on, you can check out some of the projects [here](https://github.com/ipfs/awesome-ipfs).

A couple of years ago, [someone copied](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6) the entire [cdnjs](https://cdnjs.com/) to IPFS, and was able to reduce its size from 70-something GB to 30-something - due to atomic de-duplication. 

Today, there are [proposals](http://www.cse.unsw.edu.au/~hpaik/thesis/showcases/16s2/scott_brisbane.pdf) of projects like Hadoop being implemented on top of IPFS, promising significant speedups. Many other projects are sprouting, combining Ethereum as a computing layer and the IPFS as a storage layer.

IPFS is a project conceived on the *protocol level* - so it leaves a lot of questions unanswered - like incentives. This is for the applications that will be built on top of it to figure out. Its specs are still evolving.

## Conclusion

In this article, we've covered the basic introduction to IPFS - one of the projects looking to shape internet of the future. We hope to cover more of its technical intricacies - like IPNS, ipfs-cluster, Bitswap module - and some applications built on top of the IPFS - in some of our future articles.

How exposed are you to IPFS? Have you started any of your own projects on it? Do you use any of the apps that use it? How are your experiences so far?