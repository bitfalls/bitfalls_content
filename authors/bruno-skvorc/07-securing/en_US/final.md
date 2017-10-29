After having created your [cryptocurrency wallet / address][wallet], it's important to secure it. The advice that follows may be bordering on the paranoid, but when dealing with non-trivial amounts it's better to be paranoid than robbed.

_Note: keep in mind that when talking about securing cryptocurrency, we always mean keeping the **private key** safe - that's what makes spending the currency possible. The currency itself is always stored only on the [blockchain][bc]. The difference between the methods outlined below is in how you're storing this private key._

## Ledger Nano S and Similar Devices

[Cryptocurrency][cc] is best kept safe with a hardware wallet like the [Ledger Nano S][ledger]. Note that currency is never stored **on** the device - the private key used to access and spend the currency (i.e. [sign transactions][bc]) is.

[![Ledger Nano S - Bitfalls Version](https://bitfalls.com/wp-content/uploads/2017/09/01.jpg)][ledger]

Besides Ledger, there's also Trezor, Keepkey, and other similar devices. Feel free to Google around for them, but it's our opinion that the Ledger is objectively the simplest and most practical of them all at this moment.

If this approach is out of your league due to price or apparent complexity (we do wholeheartedly recommend reading the [hardware wallet explainer post][ledger]), the following alternatives are available to you.

## Safeguarding the Private Key

When someone gets their hands on someone else's private key, they effectively become the owner of the matching address and can use it just like the original owner can. At that point, the situation becomes a race - will the owner realize the private key has leaked to a third party and move the funds in time, or lose everything? When dealing with amounts that aren't trivial, it's worth taking every possible precaution - only 100 BTC stolen in 2011 at a price of $31 would now be worth well over half a million USD.

### Paper Wallet

Transcribe the key to a piece of paper and keep the paper safe. Keep it away from web cameras and surveillance systems - both are easy to break into and a single glance at your private key through them will compromise your wallet. Write the public address of the key to the other side of the paper, and you've got a so-called "paper wallet". Effectively, it's a "bitcoin bill". To be extra safe, engrave the key and address into a metal plaque if you have the necessary tools - that'll make it fire and water-proof, too.

For simplicity, you can also print the key and address, rather than write them by hand. The same warnings as above apply, with one more: any amount that's not forgettable should be additionally secured by wiping / factory resetting the printer which was used, especially if the printer is internet-connected or there's a chance of someone else using it in the near future. Printers have a _cache_, a part of memory into which they store previous jobs, so in some cases people can restore previous printings without having the original file with them. If you'll be making such paper wallets often, it's recommended you buy a separate old-school printer - without an internet connection of cache - so it's secure by design. Under no circumstances should you feel safe printing paper wallets in a print/copy shop.

Another alternative is printing a QR code. This is what most people do because it's arguably the most practical kind of paper wallet - just scan the key and it's loaded into any machine. It's also the least secure, though. QR codes can be easily read from a distance by simple scanners and cameras, so you need to be extra careful about that. To turn a bit of text into a QR code, you can use the [QR Code Generator](https://www.the-qrcode-generator.com/) which works without an internet connection. This is important - the last thing you want is your key being sent to a server of some kind to be converted into a QR code - you never know if the server is saving it into a database on the side. It's recommended you open this generator only in a clean extension-free browser you don't usually use, like Firefox. It's also recommended to turn off the wifi or otherwise disconnect from the internet once the page loads, just in case. The risk of having the key stolen is simply too great.

![QR paper wallet for bitcoin](https://bitfalls.com/wp-content/uploads/2017/09/02-2.png)

### USB / CD / DVD

Copy your private key and address into a text file, and save it onto a USB stick or an optical medium like a CD or DVD if your computer still possesses the hardware needed to read those. Store the medium into a safe place and **only** load it into your own computer. You don't want someone else's malware eating into your assets! If possible, secure the files with a password - a tool like [7zip](http://www.7-zip.org/download.html) can help.

Keep in mind that both USB drives and optical media have a shelf lifetime of around 10 years maximum. It is advisable to make multiple copies, in addition to a paper wallet, if your intention is to store your cryptocurrency for a long time.

### Additional Don'ts

- **never** store your private key on an internet-connected computer, or a cloud service like Apple Cloud, Google Drive, Onecloud, etc. You never know who'll manage to break in and when.

- **never** send your key via email or an instant messaging service like Whatsapp, Viber, etc.

- **never** type your private key into any website's form for any reason, unless you're trying to make a transaction. If you suspect foul play, [ask us if it's safe to proceed](mailto:contact@bitfalls.com) before doing anything else - and never, ever give your private key to us. **We will never ask you for your private key for any reason whatsoever.**

- **don't** fall for promises of secure storage in Earth's orbit like [these](http://connectx.com/). The safest storage is a Ledger, or alternatively an engraved metal plaque in your desk's locked drawer or safe.

## Conclusion

Cryptocurrency wallets are trivial to generate, but almost impossible to secure. Be careful with the way you store your private keys - your savings and investments depend on your astuteness.

If you have any other suggestions for safekeeping private keys, please let us know in the comments!

[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[ledger]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/