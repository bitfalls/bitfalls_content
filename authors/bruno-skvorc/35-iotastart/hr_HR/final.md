U ovom ćemo članku proći kroz proceduru počinjanja s IOTA [kriptovalutom][cc]. Proći ćemo kroz proces instalacije [novčanika][wallet] na desktop računalo (pročitajte [ovaj članak][exchangesbad] da saznate zašto ne na mobilni uređaj), kroz primanje IOTAe, i kroz slanje.

Detaljni opis IOTAe u smislu što je, po čemu je drukčija od drugih tehnologija, i za što služi dolazi uskoro u zasebnom članku.

## Wallet

Najsigurniji način za upravljanje svojom IOTAom je preuzimanje službenog [novčanika][wallet]. Ako nemate namjeru upravljati svojom IOTAom (slati i primati), Cold Storage (vidi dolje) je bolja opcija.

Preuzimite službeni novčanik s [ove poveznice][iotawallet]. Iako će slike iz ovog članka prikazivati proces na OS X operativnom sustavu, instalacija je slična na svim računalnim sistemima.

![Instaliranje aplikacije](https://bitfalls.com/wp-content/uploads/2018/01/01.png)

Nakon pokretanja instalirane aplikacije, na pitanje o tipu Node-a odgovorite s "Light Node". Da biste saznali koja je razlika između tih tipove _nodeova_ (čvorova), pogledajte [ovaj članak][nodes].

![Node type](https://bitfalls.com/wp-content/uploads/2018/01/02-1.png)

S popisa hostova odaberite bilo koji. To je popis Full Nodeova na koje se vaš Light node spaja.

Ako nemate IOTA wallet već generiran, generirajte svoj _seed_ [ovdje][seed]. Kopirajte ga i unesite u sučelje walleta u Seed polje.

Nakon unosa, opcija "Login" postati će dostupna i moći ćete ući u svoj IOTA novčanik.

![Login available](https://bitfalls.com/wp-content/uploads/2018/01/03-1.png)

![Otvoreni wallet](https://bitfalls.com/wp-content/uploads/2018/01/04.png)

## Primanje IOTAe

Da biste primili IOTAu, odaberite Receive. Na ekranu će se prikazati niz brojki i slova, te QR kod koji možete skenirati nekim uređajem kako ne biste morali ručno upisivati tu informaciju.

![Receive ekran](https://bitfalls.com/wp-content/uploads/2018/01/05.png)

Tu vrijednost pošaljite osobi/entitetu koja vam šalje IOTAu, ili ukucajte u sučelje burze s koje je šaljete.

Opcija Attach to Tangle spaja adresu primanja na Tangle mrežu IOTAe i singalizira sustavu da je ta adresa iskorištena. Za dodatnu sigurnost, to je korisno učiniti da neki napadač ne bi mogao otkriti [privatni ključ][privkey] iz javnog - jedna od [ranjivosti][mit] IOTA mreže.

Nakon što je IOTA primljena, stanje u novčaniku bi se trebalo promijeniti.

![Novo stanje](https://bitfalls.com/wp-content/uploads/2018/01/06.png)

Ako je stanje još uvijek nula a transakcija na odredišnoj platformi (burzi ili walletu) kaže _confirmed_, potrebno je promijeniti node na koji je wallet spojen. Mijenjajte ih dok ne vidite svoje stanje. To je zbog nekih [fundamentalnih problema u IOTA mreži][iotasucks].

## Cold Storage (sigurno spremanje)

Za cold storage, tj. spremanje IOTAe na sigurno za dugoročne investicije, najbolje je koristiti [papirnati novčanik][paper]. IOTA papirnati novčanik lako se može generirati putem sučelja [ColdStorage Tools][iotacs].

![IOTA paper wallet]()

Nakon što pošaljete IOTAu na adresu generiranu tim generatorom, vaša IOTA će biti spremljena na način koji nema pristup internetu.

## Slanje IOTAe

Kod slanja, vaš IOTA wallet zapravo treba potvrditi druge dvije transakcije da bi njegova postala validna. Nakon toga, neki drugi wallet treba potvrditi tu transakciju koja je upravo izašla iz vašeg novčanika, i tako dalje. Time IOTA omogućava prijenose bez provizija i troškova, ali brzina prijenosa ovisi o sreći i brzini računala na kojem se wallet nalazi.

Da bi se IOTA poslala iz wallet softvera, dovoljno je otvoriti wallet, unijeti adresu na koju šaljete pod recipient, i poslati.

_Napomena: jedinice i, Ki, Mi, Gi, Ti se odnose na veličinu. K stoji za kilo, ili tisuću. M je mega, G je giga, T je tera. `i` bez ičega je obična jedna "IOTA". Kada šaljete IOTAu, obično zapravo šaljete Mi._

![Slanje iz walleta](https://bitfalls.com/wp-content/uploads/2018/01/07.png)

Poslana transakcija pojaviti će se u History. Ukoliko dugo vremena pokazuje status _Pending_, znači da se čeka na obradu. Možete pokušati ponoviti slanje transakcije klikom na _Show Bundle_ i zatim _Rebroadcast_, no ako previše vremena prođe bez da transakcija bude potvrđena (Confirmed), morati će biti u potpunosti ponovljena (_Replay_).

![History](https://bitfalls.com/wp-content/uploads/2018/01/08.png)

Za slanje iz papirnatog novčanika potrebno je unijeti privatni ključ papirnatog novčanika u wallet softver koji će tada imati kontrolu nad tom IOTAom. Budući da se na paprinatom novčaniku nalazi Seed s početka ovog članka, proces je identičan - nakon unosa tog seeda s papirnatog novčanika u sučelje Walleta, wallet ima kontrolu nad IOTAom na tom papirnatom novčaniku.

_Napomena: Budite pažljivi s ponovnim iskorištavanjem papirnatih novčanika. Zbog sigurnosti, bolje je uništiti papirnati novčanik u potpunosti nakon svakog korištenja i napraviti novi. Uvijek prenesite cijeli iznost sredstava s vašeg novčanika na novo-generirani kako biste bili najsigurniji._

## Zaključak

Početi s IOTAom je izuzetno lako ako se koristi službeni softver i/ili kvalitetni pomoćni alati poput [ColdStorage Tools][cst].

Ukoliko naiđete na neke probleme prilikom generiranja walleta ili primanja / slanja IOTAe, slobodno nam se javite ili ostavite komentar ispod ovog članka. Zapamtite - nije pametno držati kriptovalute na računama burzi, jer burze mogu preko noći nestati s vašim valutama. Više o tome [ovdje][exchangesbad].

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[paranoia]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[hw]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[mew]: https://myetherwallet.com
[paper]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[ledgershop]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[exchangesgone]: https://bravenewcoin.com/news/36-bitcoin-exchanges-that-are-no-longer-with-us/
[cst]: https://coldstorage.tools
[iotacs]: https://coldstorage.tools/iota
[privkey]: https://bitfalls.com/hr/glossary/#private-key
[bitcore]: https://bitcoin.org/en/bitcoin-core/
[electrum]: https://electrum.org/#home
[Abra]: https://www.abra.com/
[exchangesbad]: https://bitfalls.com/hr/2018/01/01/why-you-shouldnt-keep-your-cryptocurrency-on-an-exchange
[iotawallet]: https://github.com/iotaledger/wallet/releases
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[seed]: https://ipfs.io/ipfs/QmdqTgEdyKVQAVnfT5iV4ULzTbkV4hhkDkMqGBuot8egfA
[mit]: https://www.media.mit.edu/posts/iota-response/
[iotasucks]: http://archive.is/0PrTf