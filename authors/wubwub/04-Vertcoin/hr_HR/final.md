Vertcoin, što je? Kako funkcionira? Zašto je bolji od Bitcoina ili Litecoina? Kako ga početi koristiti?

Ova tri godine stara kriptovaluta, pokazuje kako primjerna kriptovaluta orijentirana na **financije** treba biti. 

Vertcoin je svoj [genesis blok][genesis] dobio u 2014. godini, a od tada razvoj ove kriptovalute ne staje.

Proći ćemo kroz sve odlike koje krase Vertcoin i koje omogućuju prednost nad ostalim financijskim kriptovalutama.

## ASIC otpornost

Najveća prednost Vertcoina je otpornost na [ASIC rudare][ASIC]. Ovo onemogućuje centralizaciju rudarstva i stvaranje rudarskih kartela, što znači da svatko od nas može biti kompetitivan rudar koristeći grafičke kartice u računalu. Za razliku od Bitcoina i Litecoina gdje je obavezno imati ASIC rudar, jer inače je ne isplativo.

### Blokovi i naknade
U Bitcoinu i Litecoinu, većina [nagrada iz blokova][blockreward] i [naknada za transakcije][transactionfee] ide Kineskim rudarima koji imaju velike farme ASIC rudara, a time ostalim rudarima ostaju samo mrvice od kruha.

## Promjena težine rudarenja

Vertcoin koristi Kimoto Gravity Well algoritam za reguliranje [težine rudarenja][difficulty].
Težina se regulira na **svakom bloku**, dok kod Bitcoina i Litecoina se regulira svakih 2016 blokova. Ovim načinom reguliranja kreacija novih Vertcoina može pomno pratiti [hash rate] kako dolazi i odlazi. 

Kad dođe do priljeva novih rudara (većinom zbog porasta u profitabilnosti), težina se povećava, a kad se profitabilnost smanji i rudari koji trče za profitom prijeđu na drugi profitabilni coin, tada dolazi do usporavanja mreže zbog smanjenja hash rate-a sve dok ne dođe do prilagodbe težine.

## Konsenzus

Nadogradnje na mreži nisu zadržavane od strane velikih rudara kao što smo vidjeli sa SegWit-om na Bitcoinu.

## Segregated Witness (SegWit)

[Blockchain] nije pretjerano skalabilan, pa kako bi proširili kapacitet blokova i mreže, kreativni developeri su osmislili [SegWit]. Cilj ove tehnologije je da proširi kapacitet blokova tako da iz transakcija makne potpis, koji punim čvorovima šalje odvojeno.Više o SegWit-u pročitajte [ovdje][Segregated Witness Članak].

## Lightning Network

Tehnologija je slična i ima istu namjenu kao [Raiden mreža][Raiden] na Ethereumu.
Ukratko, Lightning mreža pomoću pametnih ugovora i platnih kanala omogućuje masovni skok u transakcijama koje su prvotno off chain, time su omogućene i mikrotransakcije jer su transakcijske naknade ne postojeće, na kraju se sve pošalje na blockchain u jednoj transakciji za koju se plati naknada.

Za više detalja pogledajte [ovaj video][LightningNetwork]

## Atomic Swaps

Sve kriptovalute koje su fork Bitcoina podržavaju gore navedene značajke, uključujući i atomic swaps, koji nam omogućavaju da npr. zamijenimo naše Vertcoine za Bitcoine bez ikakve mjenjačnice ili burze.

Postoje on chain i off chain atomic swaps, trenutno se radi na razvoju off chain atomic swaps putem Lightning mreže, upravo zbog manjka naknada i instantnih transakcija.

## Stealth adrese

Vertcoin će imati svojstva koja će povećati stupanj privatnosti na javnom blockchainu.
Ova značajka je još uvijek u razvoju.

## Novčanik

Na raspolaganju imate više novčanika

* Core wallet
* Electrum wallet
* Web wallet
* [Ledger hardware wallet][Ledger]

*Svi softverski novčanici su dostupni na [Vertcoin.org][vtc]*

*Ako posjedujete Ledger novčanik, Vertcoin aplikaciju možete skinuti na Ledger Manager aplikaciji.*

*Opaska: Web wallet u vrijeme pisanja članka __ne podržava__ SegWit adrese. *

## Rudarenje

[Ovdje][rudarenje] možete pronaći sve upute o rudarenju Vertcoina na Vašem računalu.

## Gdje kupiti?

Vertcoin možete kupiti na mjenjačnicama poput [Bittrex-a][bittrex], [Poloniex-a][Poloniex], a možete ga kupiti i od [nas][buyvert].

## Zaključak

Vertcoin ima solidan tim developera,  jasan [roadmap], i trenutno je "drama-free".
Projekt je pun potencijala, za koji se nadamo da će znati iskoristiti.

No, postoji li mogućnost da Vertcoin kroz nekoliko godina postane sve dominantniji na tržištu? Možda čak i pretekne kralja kriptovaluta, Bitcoin?

Što Vi mislite? Recite nam u komentarima.

[genesis]: https://bitfalls.com/hr/glossary/#genesis-block
[ASIC]: https://bitfalls.com/hr/glossary/#asic
[blockreward]: https://bitfalls.com/hr/glossary/#block-reward
[transactionfee]: https://bitfalls.com/hr/glossary/#transaction-fee
[difficulty]: https://bitfalls.com/hr/glossary/#difficulty
[hash rate]: https://bitfalls.com/hr/glossary/#hash-rate
[Blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[SegWit]: https://segwit.org
[Raiden]: https://bitfalls.com/hr/2017/10/02/ethereums-development-roadmap-metropolis/#raiden-network
[LightningNetwork]: https://www.youtube.com/watch?v=MpfvhiqFw7A
[Ledger]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[vtc]: https://vertcoin.org/#features
[rudarenje]: https://www.reddit.com/r/vertcoin/comments/68pmmy/setup_guides/
[bittrex]: https://bittrex.com
[Poloniex]: https://poloniex.com
[buyvert]: contact@bitfalls.com
[roadmap]:https://trello.com/b/RbsKPeGw/vertcoin-roadmap