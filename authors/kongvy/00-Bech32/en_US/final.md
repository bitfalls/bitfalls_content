#Skeptical about Bech32? Here are three important reasons why you should go for it.
![man buying ripple on phone](https://burst.shopifycdn.com/photos/buying-cryptocurrency-ripple-on-phone_373x.progressive.jpg)   
Bitcoin is becoming more popular in the cryptocurrency market, thanks to the developers who work so hard to ensure constant improvement in Bitcoin technology. One of the greatest improvements in recent times is the invention of Bech32 [address](https://en.bitcoin.it/wiki/Address) format which only started getting popular this year. Although this address format holds better promises than similar segwit addresses like [P2SH]( https://bitcoin.org/en/glossary/p2sh-address), most people have been careful about adopting it for public use. We will be discussing this new address format in detail and help you to see its advantages  and how to start using it for a better Bitcoin transaction and trading experience.  
##Background on segwit addresses  
Just like the name of a bank account holder, the bitcoin network uses an address to [send and receive bitcoin]( https://bitfalls.com/2017/09/01/send-receive-bitcoin/). When bitcoin was first introduced, it had many challenges just like any new technology, and one of the major problems was how to stop the alteration of transactions on the blockchain. 
Every transaction on the Bitcoin Network has a unique [transaction ID](https://www.reddit.com/r/Bitcoin/comments/1vigqc/simple_question_whats_a_transaction_id) (txid) which looks like this: **4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b**. _**By the way, this is the txid of the first bitcoin transaction ever done on the bitcoin network in 2009._** Every transaction also has a digital signature and a script from both the sender and receiver of the bitcoins.   
The signature serves as proof that the sender of the bitcoins actually authorized the transaction. The sender’s (input) script sets conditions that must be met to be able to spend the bitcoins while the receiver’s (output) script meets those conditions.   
![bitcoin coin on bills of cash money](https://burst.shopifycdn.com/photos/bitcoin-coin-on-bills-of-cash-money_373x.progressive.jpg) 
Before segwit addresses came, miners calculated txids using all three components of the transaction (txid, signature and script), which was a serious problem majorly because any changes made in the signature or script could tamper with the txid. This makes the receiver unable to spend the output because the transaction will be confirmed with a different txid.   

Let me illustrate with three bitcoin characters. Let’s say Alice sent a small amount of bitcoin, the amount for a cup of coffee 0.00015 BTC to Bob with a txid 4Q12…yT3W and the miner who added the transaction to a block, or a node in the network altered the txid to rT12…Ec4G. Bob will receive the bitcoin without any problem but the transaction will be confirmed with rT12…Ec4G as txid instead of 4Q12…yT3W.  
 
This phenomenon is called transaction malleability which literally means “the ability of the transaction to bend”. The problem is that Bob may deny receiving the bitcoins and demand another payment or be honest and acknowledge receipt if he is a nice guy. The network may also initiate a fresh transaction sending Bob another 0.00015 BTC which he may decide to send back to Alice or keep it. That is if our dutiful miners or another node doesn’t alter the txid again.  

Another problem arises if Bob decides to send the output he received from Alice to Joe before the transaction is confirmed on the blockchain. Joe will not be able to receive the amount because the transaction will be invalid. In other words, it will be rejected because Alice’s transaction to Bob was altered. It is left for Bob to decide whether to send Joe another amount or not.   

This makes it risky to spend output from an unconfirmed transaction since the txid could be altered, thus making subsequent transaction invalid on the Bitcoin network. Segwit addresses solve this problem by isolating the signature and script of a transaction and putting them in a separate “structure” while the txid moves alone on the blockchain.   
![man reading hackernoon bitcoin article](https://burst.shopifycdn.com/photos/man-reading-hackernoon-bitcoin-article_373x.progressive.jpg) 
The signature and script are the malleable part of the transaction called “witness” and they are “segregated” from the txid, thus the term Segregated Witness. Users with segwit enabled wallets need not be scared of spending bitcoin from yet to be confirmed transactions because they are sure the txid cannot be changed.   

This is a great relief for bitcoin users and investors all over the world. Segwit addresses typically start with “3” while but another group called traditional segwit start with bc1, known as Bech32 which we will discuss shortly. 
Other benefits of Segwit addresses
 
The main idea behind segwit was to deal with transaction malleability which was largely successful, but in addition to the prime purpose, other benefits also came with the improvement.   
![putting bitcoin into piggy bank](https://burst.shopifycdn.com/photos/putting-bitcoin-into-piggy-bank_373x.progressive.jpg) 
One of the benefits is the increase in transaction volume. Initially, transaction volume was 1MB maximum but with the segregation of the witness (signature and script), more room is created to include more transactions in a block so segwit addresses have a maximum volume of about 4MB. This is helpful in reducing transaction traffic which mounts so much pressure on the network.  

Secondly, because transaction volume is increased, there is a drastic reduction in transaction fees. This is because block size determines transaction fees and not the amount being sent.  Since segwit addresses isolate the signature and script from the txid, it costs much less to carry out transactions than for non-segwit addresses.  

###**Why you should go for Bech32** 
 
Although Bech32 is also a segwit address, it belongs to a group called traditional segwit addresses. I won’t bother you with the details but traditional segwit like Bech32 address starts with bc1 while the old segwit like P2SH start with 3.   

If you have tried to send or receive bitcoins from your wallet and you saw your address starting with bc1, congratulations, you already have Bech32 on your wallet. If not, don’t worry, we will give you reasons why you should go for it and how so that you will start enjoying the benefits we will discuss now. These benefits are:    

**1.	Lower transaction fees:** Using segwit enabled wallets to carry out transactions make transactions much cheaper than non-segwit addresses, but transactions with Bech32 are even cheaper. This is because the network charges transaction fees based on transaction size not the amount like I mentioned earlier. 

For instance if Alice sends Bob 1BTC in a simple transaction, the fee will be less than Alice paying three of her staff X, Y and Z a total of 0.5 BTC in a single transaction because the transaction size is bigger than the first, even though the amount in the first transaction is bigger. Native Bech32 saves more space than P2SH, whether it is a simple transaction with one input and one output or with one input and three outputs as in the second transaction here.  
![filing taxes](https://burst.shopifycdn.com/photos/filing-taxes_373x.progressive.jpg)  

**2.	Higher error detection:** Bech32 has an error detection ability that BCH Code confers on it. This feature is so powerful on Bech32 that BCH was included in the spelling of **“Bech”**. It able to detect up to 4 errors when typing an address and its probability of failing is 1 in a billion.

In other words, Bech32 will only fail to detect up to four errors in an address once in a billion transactions. In reality, is there a real chance that such incidence is possible? Of course not. This is another reason you should go for this address format. 

One thing about the bitcoin network is that once you send your coins to a valid address or even an invalid address, the network recognizes the transaction as valid even if it is not the address you intended sending to and the funds are lost forever unless the recipient is kind enough to send the amount back to you. It is worse if the address is not a valid address. The funds are gone forever and no one has access to it anymore. Bech32 prevents this by detecting error in the address you are trying to send your bitcoin to.
 
**3.	No case sensitivity:** A typical P2SH address looks something like this: 347N1Thc213QqfYCz3PZkjoJpNv5b14kBd. Notice the random mixture of capital and small letters in the address. If you type a small letter in the address as capital or vice versa, the system either rejects it or sends your bitcoins to the wrong person if what you typed matches a valid address or to a non-existent address.

Secondly, imagine the difficulty you would experience when reading this address out loud. You will have to mention which letter is small and which is capital to get it right. Stressful isn’t it? Now this is a typical Bech32 address: bc1qar0srrr7xfkvy5l643lydnw9re59gtzzwf5mdq. Did you notice any difference? Both are a mixture of numbers and letters but Bech32 letters are all small. Now try to read this out loud. You don’t have to say letter “q” is small and “a” is capital because they are all small.     

This feature of Bech32 makes it easier to write and read addresses out loud and reduces your chance of making a mistake, a good reason to consider going for this address format.  
![crypto investor holding btc coin](https://burst.shopifycdn.com/photos/crypto-investor-gold-btc-coin_373x.progressive.jpg) 
###How to start using Bech32
Now that we have seen the enormous advantage of Bech32 over older segwit addresses, you may be anxious and already asking how you can start using the address. Well, one of the ways you can start enjoying this revolutionary address format is by downloading and installing software wallets that have adopted the format. For online wallets, just sign up online and for hardware wallets, well, you have to buy them.  

For the bitcoin gurus who are familiar with the use of codes, there are codes used to activate Bech32 on wallets but since this article is meant to benefit those venturing into Bitcoin for the first time, the following wallets and exchanges have adopted Bech32 address format so you can choose one to use for your transactions or trade.   

You don’t need to do any programming, the developers have done the heavy lifting for you. Just install the wallet on your device if it is a software or buy it if it is a hardware wallet and you are good to go! 
 
####Software wallets that support Bech32 addresses
 According to [Bitcoin Wiki]( https://en.bitcoin.it/wiki/Bech32_adoption)
, the following wallets and exchanges have adopted the use of Bech32 and you can track the progress of adoption there. Bitcoin Core, Bitcoin Knots, Samourai Wallet, Coinomi, Electrum, JoinMarket, GreenAddress, Breadwallet, and BTC.com. 
The first four in the list both send and receive with Bech32 while the rest only send.  
![wallet cash](https://burst.shopifycdn.com/photos/wallet-cash_373x.progressive.jpg) 
####Hardware wallets that support Bech32 addresses
Hardware wallets usually work with software wallets to send or receive funds so hardware wallets in this case also use Bech32-enabled software wallets to send or receive bitcoins. 
If you want to use them you will need to install the software wallet they work with. Trezor, Ledger and Digital Bitbox are the hardware wallets that support Bech32, all of which work with Electrum and all of which send and receive bitcoins with the address.   

I would go for these ones because of their tested security and the ability to both send and receive with the address.  
![bitcoin accepted here printable](https://en.bitcoin.it/w/images/en/e/ed/Bitcoin_accepted_here_printable.png) 
####Web wallets that support Bech32 addresses
For those willing to take the risk of working with web wallets, they are not left out of the Bech32 revolution. Holytransaction which only sends with the address, and Coinb which both sends and receives bitcoins with the address are the web wallets that support the address format. Although they are the most vulnerable of wallets, I think it’s better to enjoy the benefits of Bech32 if you must use one so try one of these.  

####Exchanges that support Bech32 addresses
 
For those who trade bitcoins, it is very important to know which exchanges currently support sending and receiving coins through Bech32 addresses for easy withdrawal and deposit of funds.
 
Of course you must have a Bech32 enabled wallet to do that. The following are the exchanges that currently support Bech32 addresses.  

1Fox, Anycoin, Bitbargain.co.uk, Bittylicious, Coinbase, CoinFalcon, Fly.me, GDAX, HODI HODI, Liberalcoins* and Walltime*. Exchanges with asterisk both send and receive while no asterisk only sends.   

##Conclusion 
By now you have seen clearly why you should work with Bech32 address formats. The wallets and exchanges above enable you to use it for your transactions. Working with it will be a good idea to save you the cost of transaction if not any other thing. The more people adopt this new address, the faster the benefits will spread on the bitcoin network so help to spread these benefits and make the bitcoin experience greater!












