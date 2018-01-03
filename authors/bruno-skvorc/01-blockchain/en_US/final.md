What is *the blockchain*?

How does it work, why is it popular, and why do so many people claim it'll revolutionize the world?

In this article, we'll explain blockchain technology on a banal example that's nonetheless valid for most cryptocurrencies currently in circulation. Not familiar with the concept of cryptocurrency? See [here][cryptocurrencies]!

## Mario and Luigi

Mario needs to send $100 to his brother, Luigi, because Luigi being Luigi, he got into some debts at the other end of the world.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-01.png" alt="Luigi in debt" width="350">

Mario walks into the bank and says "I'd like to send $100 to Luigi". The teller says "Account card please.", "ID please", and "done", in that order.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-02.png" alt="Mario sending money to Luigi through the bank" width="350">

In this *centralized* scenario, the bank is the **_central_** authority over Mario's and Luigi's money. Both Mario and Luigi trust the bank to transfer the amount, and believe the numbers shown on their bank account statements. They trust the bank despite the fact that all the bank has to do is - change a number in a database. It's all digital, after all.

However, when we're dependent on such a central authority, that authority poses a certain threat. It can disappear with our money, it can be evil and not increase Luigi's value while decreasing Mario's value, thereby keeping the difference, or it can just be clumsy and make a mistake. Our finances depend directly on their competence.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-03.png" alt="A thief walking away with bank money behind the teller" width="450">

One way of preventing such scenarios is skipping the bank entirely and having our own system of tracking value and the travel of value from one location to the next.

Imagine a piece of paper on which we're noting down the status of our bank account. If only Mario and Luigi are using that system, it's hard to keep it fair - if one of them becomes greedy, the system is already compromised. Hence, such a *distributed* (non-*centralized*) system needs to have enough participants to make it viable - a minimum of three.

## Papers

Let's assume we have 5 participants: Yoshi, Mario, Luigi, Wario, and Bowser, and that each of them has their own piece of paper.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-04.png" alt="Each participant has his own piece of paper" width="550">

Mario wants to send $100 to Luigi. To do this, he lets everyone know (by loudly proclaiming): "I'm sending $100 to Luigi! Please take a note, everyone!"

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-05.png" alt="Mario sending money to Luigi and yelling it out" width="550">

At that moment, every participant checks Mario's account to make sure he's got enough value on it to send to Luigi (yes, every account's status is public) and if so, writes this transaction down on their piece of paper. Transaction of this type are written down onto the participants' pieces of paper until they run out of room. In other words, **every** transaction between **any two people** is logged on **every participants paper**.

Before we file the filled up paper away into a folder or filing cabinet and grab a new, blank one, we need to seal the filled one with a special code.

## Seals and mining

This "seal" guarantees that the contents of the paper are true.

How do we get this seal? With a special algorithm (mathematical operation) which, when we feed it some input data, always produces the same output *if the input data is the same*.

Let's take the following as an example:

X1 + X2 + ... Xn = Z.

In other words, a simple sum.

Let's assume that our paper's values are *true and valid* (i.e. all the transactions are confirmed) if and only if a given summation operation produces the number 10000.

1000 + 6000 + 3000 = 10000.

In this case, the input data is 1000, 6000, and 3000, while the _seal_ is 10000.

Okay, so let's assume that our participants above came to the following agreement: if, when you sum up all the numbers on the paper and **a specific** combination of other numbers, you get 10000, then the transactions on that paper are valid and can be considered confirmed.

For example, if the paper contains the following 5 transactions:

- Mario -> Luigi = 100
- Bowser -> Yoshi = 200
- Yoshi -> Luigi = 100
- Mario -> Yoshi = 500
- Luigi -> Wario = 100

The sum is 1000, so we're looking for a number which gives 10000 when added to 1000. This remaining 9000 can be achieved with many combinations:

- 5000 + 4000
- 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000
- 2000 + 3000 + 2000 + 2000
- etc...

A computer can't intuitively tell which numbers will produce the desired number. To get to this result, a computer has to _randomly guess_ between different combinations of numbers under 10000 until it gets one combination that produces 10000. Thus, the first among our participants to correctly guess a combination of numbers which produces 10000 when summed with all the transaction values on the paper will be the one to tell everyone else the result.

Suppose that Yoshi found the combination 4000 + 5000. He tells everyone: "I've got a 10000! Try 4000 and 5000!" Given that it's very easy to verify the correctness of Yoshi's numbers by simply inputting them into the algorithm, the other participants verify this. All the other participants' papers which now, during this check, also produce 10000 when summed with 4000 and 5000 effectively validate the list of transactions in front of them. By doing this, a consensus is reached that the papers are all valid.

If someone's paper does **not** produce 10000 when summed with 4000 and 5000, we have a problem. If, for example, Bowser either purposely or accidentally logged a different transaction - say, that Mario gave Luigi $200, and not $100 - then the sum will not match the requirements.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-07.png" alt="Everyone except Bowser confirms the paper" width="550">

Bowser's paper is thereby considered invalid, and if he wants to continue participating in this system, he'll have to discard his paper, copy someone else's valid paper, and promise to be more careful in the future. On the other hand, Yoshi, who was the one who found the winning combination, gets a reward of, for example, $5 from the system. The system *produces* the $5 out of thin air as a reward for the lucky participant.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png" alt="Yoshi gets a reward, Bowser throws his paper away" width="550">

This *production* of money out of thin air is called *mining* in the cryptocurrency world.

While this was a dramatically simplified example, the only real difference from the real blockchain (beside the fact that in reality it's all digital and automatic) is the fact that the algorithm being used to produce the *seal* is different - a more complex one which can accept both numbers and letters, and outputs code like `90bdaa79bbccacf8558edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`.  

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-06.png" alt="A sealed paper" width="350">

The *seals* are called *hashes* and the algorithms producing them - like SHA256 which produced the above code - are called *hashing functions*. Try opening [this link](http://www.xorbin.com/tools/sha256-hash-calculator) and inputting any amount of text into the field. Whether you put in a single word or the entire bible, it'll always produce a hash of exactly 64 characters.

Hence, to get the hash which seals our paper, we enter into the algorithm all the transactions present on the paper. They become a hash. Since there is an infinite number of combinations of characters we can provide as input for the algorithm, guessing the original input set of data based purely on the output data is a mathematical impossibility.

Specifically, in the Bitcoin blockchain, the consensus of the network and all its participants is that as long as a produced hash (which we get from combining the last paper's hash and all the transactions of the current paper, plus a random bit of numbers and letters) starts with a given number of zeroes, it is valid. For example, if paper 1 has the hash of  `0000000000000000058edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`, paper 2's valid hash will be the one which (when the current paper's transactions and some random data are added to the last paper's hash) contains an equal number or more zeroes at the front.

To get this combination of random characters needed for producing a new valid hash, a computer must make guesses. Modern computers are very fast and easily try out thousands of combinations per second, but this still isn't fast enough given that the number of possible combinations is near infinite. As an aside, the aforementioned hash shows us that the difficulty of guessing a new one is ranked 17, because there are 17 zeroes at the front of it. In time, the difficulty will increase and a new valid hash will need more and more zeroes at the front.

When the paper of each participant is marked as valid with the hash, it is put away into a folder - a _ledger_ of sorts, and a new blank one is pulled out.

### In Blockchain parlance

In blockchain parlance...

- one paper is *a block*.
- one block contains many *transactions*.
- one block always follows a previous block, forming a chain. A _blockchain_. Validated blocks are put away into a *ledger* (synonymous with *blockchain*).
- computers guessing the combinations are called *nodes*. A node which guessed the hash combination gets a reward in the form of the blockchain's tokens - in our particular example, a few Bitcoins.
- the guessing for combinations is called *mining* because we're *digging* for new value in a big pile of random guesses. Instead of muscles for effort and pickaxes for tools, we use electricity, time, and a computer's calculating power. The characters in our story above are all in little go-carts precisely because it's all a race - he who first confirms a block with a valid hash wins, and gets the very valuable reward. So too in the blockchain world do the most powerful computers (or pools of computers) usually win the block rewards.
- the existence of a new valid hash is considered **proof of work**. This is a model that most cryptocurrencies today use in order to make easy guessing or cheating financially non-viable because of too high electricity costs. Some protocols like Ethereum are moving to **proof of stake** in which the pointless wasting of electricity is being minimized and the punishment for invalid participation is made stricter, but that's a topic for another post.


## Conclusion

All cryptocurrencies are based on _blockchain technology_. Blockchain is what makes it possible for them to be transparent, definitive (impossible to falsify or duplicate) and somewhat limited in maximum amount produced. Unlike fiat currency (USD, Euro, etc.), cryptocurrencies cannot simply be printed by their creators, except in the case of some scam currencies like Ripple (XRP) or OneCoin - more on those in another post.

Blockchain technology allows for distributed control over the financial system of a society - local or global - and helps with avoiding middlemen. This is one of the main reasons why [cryptocurrencies][cryptocurrencies] have exploded in popularity so much. Due to the distributed nature of the blockchain and millions of users all around the world all of whom serve as "accountants" and validators, many  consider cryptocurrencies to be indestructible and unstoppable. Sadly, that's a different kind of delusion, one which we'll cover later (see links in the following section).

## What next?

- [What are cryptocurrencies][cryptocurrencies] to learn what it's all about and where the value is coming from
- [Bitcoin is not unstoppable][unstoppable] to find out how easy it is to actually stop and destroy a cryptocurrency
- [Bitcoin is not finite][finite] - to learn why the theoretical limit of 21 million Bitcoin ever produced simply isn't true, practically speaking
- [Bitcoin is not anonymous][anon] - to learn why people often (incorrectly) say that Bitcoin is anonymous and useful for the black market and criminal funding
- [What is Ethereum?][eth]- to learn about the most powerful cryptocurrency today 

[cryptocurrencies]: https://bitfalls.com/2017/08/20/cryptocurrency/
[unstoppable]: https://bitfalls.com/2017/08/21/is-bitcoin-unstoppable/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[anon]: https://bitfalls.com/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
