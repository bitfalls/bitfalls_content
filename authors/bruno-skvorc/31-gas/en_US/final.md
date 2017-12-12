It is recommended you read the following materials before diving into the rest of the post in order to better understand the terminology we'll be mentioning.

- [What is cryptocurrency?][cc]
- [What is the blockchain and how does it work?][bc]
- [What is Ethereum and how is it different from Bitcoin?][eth]
- [What is mining and what's the difference between PoW and PoS mining?][pow]

Basic knowledge of programming terms (variables, loops) might also come in handy.

---

When sending a Bitcoin transaction, its fee is proportionate to its size. The more [inputs and outputs][blockex], the more expensive it is. Add to that the factor of [pending transactions][pendingbtc], and transaction fees can skyrocket based on those two factors alone.

With Ethereum, given that we're talking about a programming language within the protocol, it's possible to be very computationally demanding with very little text or code (something which would be very cheap in the BTC-verse). Let's look at this loop for example:

```sol
while (i++ < 1000) {
    j = j + i;
}
```

This loop means "for as long as `i` is smaller than 1000, increase it by 1 and then sum up `i` and `j` and write the result into `j`, then do it all again." This loop will execute 1000 times if `i` is 0 or more if it's a negative number.

To pay for this computational cost in a fair way - since it has to be executed on all miners' machines at once and they spend their resources and time on it - the concept of _gas_ was introduced. Gas is used to pay for the execution of these so called smart contracts (Ethereum programs) inside the EVM. For example, `i` + `j` above is a summation operation which costs 3 gas every time it's executed, so 3000 gas if executed 1000 times.

To explain _gas_ properly, let's first cover the _EVM_.

## EVM

EVM stands for _Ethereum Virtual Machine_. But what is a virtual machine anyway?

### Virtual Machine

A virtual machine is software running on a specific computer which contains another operating system completely encapsulated inside the main one. A virtual machine allows you to, for example, run Windows inside of Linux, Linux inside of Windows, Windows on OS X like in the image below, or any other combination.

![Windows inside OS X](https://bitfalls.com/wp-content/uploads/2017/12/01.jpg)

We use virtual machines to separate the environment in which we do our everyday computer use from the environment we work or program in. This lets us keep viruses at bay (they have no way of breaching the virtual machine and getting to the main operating system), helps prevent infinite loops from crashing our main operating system, and holds hard-drive corruptions like the infamous WannaCry ransomware at bay. Additionally, VMs let us use Windows games on Linux, for example, or allow us to program in different versions of the same programming language's environment easily, without mixing them up.

### EVM

The Ethereum Virtual Machine is built into the software running on the Ethereum protocol. It executes smart contracts - Ethereum programs written in the Solidity language. The EVM is contained in the [full nodes][nodes] of the Ethereum network, inside of which it executes these Ethereum-user-written programs.

Any [miner][mining] of Ethereum simultaneously executes smart contract code. What this means is that Ethereum programs (dapps - decentralized apps) are executed on everyone's computer at the same time (decentralized).

Execution of these programs isn't free, however. Miners spend their own electricity, time, and hardware to do this. To pay them for their effort of executing computer instructions (like "store the value 5 into the variable X"), the concept of _gas_ was introduced.

## Gas, Ether, and GWei

Gas is a unit of cost for a particular operation a computer needs to execute, and it executes this instruction when we broadcast a transaction which contains an Ethereum program in order to run a _dapp_. For example, summing two numbers costs 3 gas. Multiplying them costs 5 gas. Storing a 256bit word into the blockchain costs 20000 gas, which means storing 1kb of data costs 640000 gas.

Just like the USD has cents, so too does ether have its own basic unit: wei. If we take wei as the basic unit of ether, we get the following table of definitions:

|unit                                 | wei |
|-------------------------------------| --- |
|**wei**                              | 1   |
|kwei / ada / femtotether             | 		1.000| 
|mwei / babbage / picoether           | 		1.000.000| 
|**gwei** / shannon / nanoether / nano| 	1.000.000.000| 
|szabo / microether / micro           | 		1.000.000.000.000| 
|finney / milliether / milli          | 		1.000.000.000.000.000| 
|**ether**                            | 		1.000.000.000.000.000.000| 

According to [this informative site][ethgas], the current average price of gas is 10 GWei (10 gigawei). Seeing as 1 GWei is one billionth of an ether, the aforementioned cost of storing a 1kb word is 640000 * 10, which is 6.4 million GWei. That amounts to 0.0064 eth which, at a price of $450 per ether, amounts to around $2.88.

The text from the beginning of the above table all the way to **>>this specific marker<<** is around 1kb. So storing this little bit of text into the blockchain actually costs $2.88. However, that's just the storage cost! Our smart contract could also have some logic, like summing or multiplying and then storing numbers, or triggers that activate on a specific mined block etc. Obviously, storing data into the blockchain itself is incredibly expensive. Storage is better off in BigchainDB or [IPFS], while blockchain is a better solution for global processing and verification of that data.

### Why Gas?

Why pay costs in gas and not ether directly?

All the gas prices of all the possible operations the EVM can perform are hard-coded in the Ethereum protocol and in the [clients][cli] (programs) we connect to it, like Geth, Eth, Parity, etc. If the code listed them in ether, then we'd have to update the code every time ether's value fluctuated to keep the price of computing efforts in a normal range and keep the system usable, which is obviously unsustainable.

By adding this _gas_ layer on top of the costs, and paying for gas with GWei, we are given the option to alter the amount of gas to use in a transaction and the amount of money to pay for it. It's fully under our control, without throwing the system off balance.

This leads us to our last section.

### Limit / Cost vs. Price

_Gas limit_ is the **maximum amount** of gas we're willing to spend on a transaction. Most software we use to broadcast Ethereum transactions has the ability to auto-estimate the amount of gas that'll be necessary to execute a function. It'll usually suggest a figure right off the bat. For example, simple monetary A->B transactions usually need only 21000 gas. More complex ones which call specific smart contract functions might run into hundreds of thousands or even millions of gas. The spent amount of gas is called _gas cost_.

We, as a user, can modify the amount of gas we want to spend on a transaction and reduce it, but if the transaction runs out of gas during execution, we lose the gas we sent in. It's been spent and the transaction is rejected. On the other hand, if we provide more gas than is needed, the rest is refunded to us. Hence, it's always better to send more gas than you might need to execute a transaction.

_Gas cost_ is the GWei price per unit of gas.

Thus, the total cost of an Ethereum transaction is actually the amount of necessary gas multiplied by the price in GWei per gas unit. This is the **maximum** transaction fee we'll pay - any extra gas is refunded, so fees are often vastly overestimated.

Let's look at an example.

![25 Gwei](https://bitfalls.com/wp-content/uploads/2017/12/02.png)

In the above image, we're executing a transaction which, due to its complexity, estimates it'll need 135963 gas. With a 25 GWei price, the maximum transaction fee we'll pay is $1.57, which is trivial when looking at the total amount we're sending (0.38 eth = $178). If we raise the price of gas to 250 GWei, the transaction becomes proportionately more expensive:

![250 GWei](https://bitfalls.com/wp-content/uploads/2017/12/03.png)

A higher tx fee effectively encourages miners to process our transaction before others in the queue, thereby speeding up execution. If we're not in a rush, we can leave the price of gas at its starting value and the transaction's confirmation shouldn't take more than 10 minutes. But if we're in a rush and want it done in seconds (if, for example, we're dealing with an auction), it's easy to increase the price of gas and sacrifice some money for a guarantee of success.

## Conclusion

Gas is the unit of work expended per computational operation in the Ethereum Virtual Machine. It's paid for in ether, the token of the Ethereum protocol, and each computational operation has a different gas cost. The gas price (in GWei or 1 billionth of an ether) varies according to the network congestion and the user's preference for a speedy confirmation.

For a smart contract which we want to deploy on the Ethereum network, two terms are important: gas limit, and gas price. Gas limit is the maximum amount of gas we're willing to spend on executing the transaction. The amount of gas actually required (known only once the transaction has been executed) is called _gas cost_. Gas price is the price per unit of gas, expressed in GWei (or billionths of ether). The total cost of a transaction will be the product of gas cost and gas price, while the maximum transaction fee will be the product of gas limit and gas price. The difference is refunded to the transaction's sender to keep the system fair and usable.

[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[progeth1]: /
[pow]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[mining]: https://bitfalls.com/glossary/#mining
[ethgas]: https://ethgasstation.info/
[blockex]: https://bitfalls.com/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[pendingbtc]: https://blockchain.info/unconfirmed-transactions
[nodes]: https://bitfalls.com/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[ipfs]: https://bitfalls.com/2017/10/29/ipfs-just-take-internet-back/
[cli]: https://www.ethereum.org/cli