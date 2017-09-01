## Generating an address

One of the simplest ways to generate an address which can accept Bitcoin is by going to [BitAddress.org](https://www.bitaddress.org).

Move your mouse or type in some random numbers and letters into the provided field until the counter says 100% (this is so that an element of randomness is introduced into the process, making things harder to guess for machines). The screen will then display something like this:

![Generirana adresa](https://bitfalls.com/wp-content/uploads/2017/08/Screenshot-2017-08-23-17.51.44.png)

The green "Share" part starting with 195 is the public address of this wallet. You can check how many bitcoins it has at any moment, and who sent them where to/from by going [here](https://blockexplorer.com/address/195sYZTRik2y3gidQZ3svoU7NexoLPJopr). This is the address you give someone so they can send you bitcoins.

The red part (starting with L3SR) is the private key which you should never let anyone else see. You use this to send currency to another address.

It's best to save it in a text file, put it into a USB stick and store that stick into a drawer of a safe. Better yet, write it on a piece of paper, or engrave it into a bit of metal to make it fire-proof, then store that.

## Receiving BTC

To receive BTC, just put the public part of the address you previously generated (the one starting with 195 in our previous example) into the recipient field, or send it to the person sending you funds. Note that the person sending you funds **never** needs your private key - if they ask for it, they're trying to rob you. Please [report][mail] such instances to us.

## Sending BTC

If your BTC is in an account on an exchange site, there should be a "Send" or "Withdraw" option somewhere. Use it, input an address into the recipient field, and you're done.

To send BTC from an address the private key of which you own, you need software to generate and sign a transaction. You'll need to import the private key into such software. Due to the security implication of giving a third party your private key, it is recommended you move the entirety of the funds to another address as soon as possible - either fully moving them to someone else, or sending whichever amount you intend to send, and then moving the rest to a new address.
  
Create an account on the [Blockchain.info](https://blockchain.info) site, then click on Settings -> Addresses once you reach the dashboard screen.

<img src="https://bitfalls.com/wp-content/uploads/2017/09/01.png" alt="Addresses option in the settings menu" width="350">

Click "Import Bitcoin Address".

![Import Bitcoin Address option](https://bitfalls.com/wp-content/uploads/2017/09/02.png)

The following screen will let you either scan a QR code or manually input a private key by typing it in.

![Import private key option](https://bitfalls.com/wp-content/uploads/2017/09/03.png)

Once the import is complete, your funds will be ready for sending. Click "Send" at the top of the screen to do so - you'll need the public address of another wallet as recipient.

## Sweep vs Import

It's important to know the difference between sweeping and importing private keys.

When you import a private key into a software wallet, you let the original user of the private key - be it you or someone else - re-import the same key somewhere else and still have access to the funds. Once the funds are spent (sent) at any imported location, they disappear from both. If you're certain that you're the only person to ever have laid eyes on your private key, importing is just fine and secure an option.

Sweeping is importing a private key and immediately moving all funds to a newly generated address. This makes the imported private key useless because it no longer contains any funds, so importing it elsewhere has no advantages. This costs money - a mining fee has to be paid - and it takes time: confirming the transaction can take hours, even days, depending on the busyness of the network at the time.

If anyone other than you has ever used or seen your private key (like if you were given a paper wallet by someone), sweeping is the safer method, no matter the cost.

## Alternatives

Due to the fact that if Blockchain.info stops working the above method will cease to work, we're listing the following alternatives:

- Blockchain.info mobile apps ([iOS](https://itunes.apple.com/us/app/blockchain-bitcoin-wallet/id493253309?mt=8) / [Android](https://play.google.com/store/apps/details?id=piuk.blockchain.android&hl=en))
- [Electrum](https://electrum.org/#home)
- [Mycelium](https://play.google.com/store/apps/details?id=com.mycelium.wallet&hl=en) Android app
- [Breadwallet](https://breadwallet.com/)
- [Bitcoin core](https://bitcoin.org/en/download)

[mail]: mailto:contact@bitfalls.com