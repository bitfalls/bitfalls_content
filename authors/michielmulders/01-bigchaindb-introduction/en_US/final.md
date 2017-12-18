# Title suggestion: Introduction to BigchainDB: decentralized asset storage on blockchain

BigchainDB is a combination of a database and a blockchain. BigchainDB tries to fill a gap in the decentralized ecosystem by providing a decentralized, scalable database. Many blockchains try to improve the amount of transactions handled per second. This article covers an introduction to BigchainDB, gives an overview of the architecture and its functioning, touches some existing problems and ends with the differences between a traditional and a decentralized database. To fully understand this article, it is key to be familiar with the concepts of a [blockchain].

## Introduction to project
In the summer of 2013, Ascribe, the company behind BigchainDB, started working on a blockchain-based intellectual property project which would enable creators to own digital art the way you own Bitcoin. After raising some money, Ascribe was able to create a ready-to-launch product in shape to serve larger-scale customers, with the glaring exception of the blockchain scalability. 

With this as a starting point, they drew on their own experience in shipping blockchain products to define three specific characteristics: decentralized, immutable and the ability to register and transfer assets. An asset can basically be anything in the form of text output. With the definitions above as a starting point, we chose an enterprise-class distributed database (MongoDB) and then built our own technology on top of that, adding those three key characteristics while improving base functionality, fault tolerance and much more. All these efforts resulted in the launch of a product called BigchainDB, a scalable blockchain database for the world.

To give a clear image of BigchainDB's capabilities, let’s start with a short story… Alice is the owner of a bike shop. She sells a bicycle to a customer called Bob and decides to store/register an asset on the blockchain with following fields:
- date
- owner
- price
- unique identifier of bicycle

Alice creates the asset and signs it with her private key. Next, she transfers the asset to Bob so he becomes the owner of the bicycle. Alice can use this asset as a prove that she actually sold the bike and transferred it to Bob. If Bob decides to sell the bicycle, he will have to transfer the original asset Alice create (transfer transaction). This is an example of the basic BigchainDB flow. 

In terms of GDPR complicance, BigchainDB is generally used as a source of verification of authenticity. Assume we store data in a central database. Next, let's create a hash of each object and store the hashes on the blockchain. Later on, we can use this hash on BigchainDB to check the authenticity of the object in the database. In addition, BigchainDB offers the possibility to set up a private or public blockchain, based upon your needs.

## Architecture
### Functioning
BigchainDB is a distributed database consisting of multiple nodes. At this point, each node contains the full copy of the ledger (full replication). BigchainDB is built on top of MongoDB, so it only accepts JSON documents which are called assets.

Each node runs the BigchainDB core driver and is capable of accepting transactions containing assets which will be placed in the backlog. They are as well responsible for creating blocks which will be passed to MongoDB to be stored as transaction blocks. 

![BigchainDB Architecture][architecture]

BigchainDB uses two types of peers (which are the voters): super-peers and normal peers. Super-peers have the right to vote for the validity of a transaction (BigchainDB instances, no human interference). Normal peers just have the right to read and write transactions containing assets. Users can only access the normal peers for reading and writing transactions.

BigchainDB comes with a clever mechanism to speed up processing of transactions. If a double spend or a bad transaction is registered, super-peers give it an ‘invalid’ label. BigchainDB won’t take the effort to remove the invalid transaction from the blockchain to speed up the process. On the other side, a transaction is defined as valid when a majority of the nodes agrees on the transaction’s validity.

Next, let me explain how BigchainDB nodes determine the validity of a transaction. First of all, they compare the structure of the received transaction with the BigchainDB transaction schema. There are small differences between a “create” and “transfer” transaction. For example, a “create” transaction should contain a “data” key to store the asset data in JSON format. The “transfer” transaction should contain an “id” key which references to an asset created earlier. All of this is done by the node itself (super-peer) because they know the exact rules.

BigchainDB provides wrappers to interact with the nodes, we call them HTTP Client-Server APIs. These wrappers provide easy-to-use functions for creating asset payloads, signage and sending them over to BigchainDB driver nodes. Those wrappers are available for JavaScript, Java and Python. 

### Traditional database vs BigchainDB
**Disadvantages Traditional Database**

- Controlled by single admin user
- Mutable
- Not designed to stop Sybil attacks, where one errant node can swamp all the votes in the system.
- No support for creation and transfer of digital assets where only the owner can transfer it.
- Not typically open to the public.

**Disadvantages BigchainDB**

- However BigchainDB is a scalable blockchain database, the transaction times are still slower than a traditional database. 

### Some Concerns
#### Storage of Transaction
A valid transaction sent to a BigchainDB cluster won’t necessarily end up being stored. Several things can go wrong, where the user has to be aware of:

1. Transaction gets corrupted.
2. Transaction gets lost on its way to the node.
3. Node might go down before a transaction is written to the blockchain.

#### MongoDB Admin User
What about an admin user, capable of removing all collections within MongoDB? MongoDB has an admin user which can’t be deleted. BigchainDB has plans to mitigate it by:

1. Locking down the admin user rights as much as possible.
2. Having all nodes inspect admin-type requests before acting on them. Requests can be checked against an evolving whitelist of allowed actions. Nodes requesting non-allowed requests can be removed from the list of cluster nodes.

### IPDB
[The interplanetary database] is a publicly available blockchain database which runs on BigchainDB nodes. For the sake of easy development, you can use the testnet of IPDB in order to avoid the setup of a local BigchainDB cluster. 

#### Difference with IPFS
[The Inter Planetary File System] wants to become a decentralized storage network working on the level of protocols. Whereas BigchainDB wants to provide a decentralized database in which each asset is queryable. 

#### Costs
The final number is a one time fee of $100 per GB. This allows BigchainDB to store data indefinitely while covering the cost of operating the IPDB Foundation. According to estimates, the size of a transaction consists of 7 kB. So, we’ll have to pay $0.0007 per transaction. The paid plan is not yet available.

In the early phases, they will run several BigchainDB nodes on instances like Amazon or Google to create the decentralized IPDB network. 


## Roadmap
BigchainDB has some big-picture goals defined:

- Improve security for core (ref. MongoDB admin user)
- Guarantee correctness of asset storage and confirmation
- Improve querying for assets through 
- Improve logging for BigchainDB core with more clear error messages
- Improve HTTP Client API with more functions
- Composable assets (group of assets)
- Roll out production net for IPDB

## Competitors
BigchainDB is certainly a unique product, and remains the most active one. However, there are some other products who try to bring a decentralized database:

**Noms**
Noms is a decentralized database philosophically descendant from the Git version control system. By default, all previous versions of the database are retained. You can trivially track how the database evolved to its current state, easily and efficiently compare any two versions, or even rewind and branch from any previous version. Noms claims they scale well to large amounts of data and concurrent clients. Noms provides a flexible query model through the use of GraphQL.

**Orbit-db**
Orbit-db is a serverless, distributed, peer-to-peer database. orbit-db uses IPFS as its data storage and IPFS Pubsub to automatically sync databases with peers. They claim to be an excellent choice for decentralized apps (dApps), blockchain applications and offline-first web applications. Data can be stored in a Key-Value store or as a Document store (JSON).

## Conclusion
Despite BigchainDB is a working product, it still has some weaknesses like the MongoDB admin user, no guaranteed transaction storage and transaction loss or corruption. On the other side, BigchainDB has succeeded in their mission to create a scalable blockchain database. The technology can be applied to many use cases to make applications tamper-resistant. The HTTP Client API is a useful tool for interacting with the BigchainDB core drivers providing functionality to create and transfer transactions. If BigchainDB succeeds in finishing their roadmap, it will become a highly attractive technology for decentralized storage. It certainly has the potential to disrupt many businesses.

[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/ 
[architecture]: ../images/01.png "BigchainDB Architecture"
[The interplanetary database]: https://ipdb.io
[The Inter Planetary File System]: https://bitfalls.com/2017/10/29/ipfs-just-take-internet-back/ 
