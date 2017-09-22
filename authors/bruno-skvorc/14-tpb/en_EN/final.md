A few hours ago the well known torrent directory ThePirateBay added [cryptocurrency][cc] mining software to their site. The cryptocurrency being mined is Monero, an anonymous alternative to Bitcoin, and it only happens on some areas of the site.

If you've noticed your computer heating up or the fans spinning crazily while browsing the site, this may be the culprit. What happens is that when you visit certain pages, a bit of JavaScript gets loaded which then fires up the mining software written by [Coin Hive][coinhive]. This hijacks your unused CPU power and uses it to mine currency. If you'd like to know how mining works in general, see [this post][bc].

![The script which initializes the miner](https://bitfalls.com/wp-content/uploads/2017/09/01-2.png)

Mining of this kind has barely any effect when few users are doing it, but when dealing with millions every day - a number which TPB frequently exceeds - things get more serious.

While TBP claim that they're doing this to keep the website alive without ads and that they're only testing this feature for the first 24 hours with no longer term decision having been made yet, anything they say should be taken with a grain of salt as their approaches to funding the site have so far been dubious at best. As an example, we can mention the popups that happen behind the scenes as you browse the page - those load porn ads, or generally just spam your computer with cookies so you can be tracked as you browse the web and your information can be used against you later on, depending on who purchased it from the trackers.

Trying to fund a website through different means is perfectly fine, but secretly usurping a user's CPU power is sneaky and evil and many users are visibly and understandably upset.

If you'd like to prevent sites from doing this in the future (not just TPB but in general), we recommend installing the [NoCoin][nocoin] browser extension (works for Chrome, Vivaldi, Opera, and Ghost). We've looked at the source code of this extension and it's 100% safe to use.

[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[coinhive]: https://coin-hive.com/
[nocoin]: https://chrome.google.com/webstore/detail/no-coin/gojamcfopckidlocpkbelmpjcgmbgjcl/related
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/