U ovom ćemo kratkom vodiču proći kroz počinjanje s popularnom [kriptovalutom][cc] Litecoin (LTC): kako je nabaviti, spremiti, i poslati.

## Pozadina

Litecoin je rana kopija ili [fork][forks] Bitcoina. Charlie Lee, autor Litecoina, bio je programer u Googleu i donedavno u [Coinbaseu][cb]. Napravio je Litecoin 2011. kad je odlučio proviriti "ispod haube" Bitcoina i naučiti što je to [blockchain][bc]. Shvatio je da s lakoćom može napraviti sustav bolji od onog koji imamo i danas u Bitcoinu, pa se tako [blokovi][block] u LTCu [rudare][mining] svake 2.5 minute, dok je teoretski maksimum ikad rudarenih Litecoina povećan na 84 miljuna (umjesto [teoretskog maksimuma][finite] od 21 miljun kod Bitcoina). 

Promijenjen je i algoritam rudarenja koji treba više radne memorije, pa ga donedavno nije bilo moguće rudariti [ASIC][l3] strojevima - računalima koja onim rudarima koji ih uspiju nabaviti daju nepoštenu prednost zbog efikasnosti.

Kada je Coinbase uvrstio Litecoin u svoju ponudu valuta, popularnost mu je dodatno eksplodirala te je sada ozbiljna dugoročna prijetnja Bitcoinu i Bitcoin Cashu.

## Kako do Litecoina?

1. [Bitfalls][buycc]: Javite nam se ako želite kupiti Bitcoin. Verifikacija nije potrebna, a veličina transakcija nema gornji limit - unutar granica razuma. Načini plaćanja su direktna uplata na devizni račun u EUR ili USD, direktna uplata na kunski račun, ili PayPal. Nakon kupnje šaljemo račun, a LTC stiže direktno na adresu koju ste nam poslali. Nikada ne zadržavamo tuđe valute, osim u slučaju zakrčenosti mreže ili kada kupite uslugu [upravljanja portfeljom][folio].

1. [Coinbase][cb]: Coinbase je jedna od prvih burzi za kriptovalute, i trenutno podržava direktne kupnje BTCa, LTCa, i [ethera][eth]. Zahtjeva rigorozne provjere identiteta i vlasništva kartice s koje se vrše uplate, i ima relativno visoke provizije, no ima najbolje korisničko iskustvo - najlakše ga je koristiti. Nakon što kupite LTC na Coinbase, spremite ga na sigurno (vidi dolje).

1. [Bitstamp][bitstamp] je operacijski slična burza Coinbaseu, samo podržava više načina uplata i više kriptovaluta. Provizije im isto tako nisu najpovoljnije, ali ih je lako koristiti, i vrlo lako i jeftino poslati valute izvan platforme na vlastitu adresu. Također zahtjevaju rigoroznu provjeru identiteta.

1. Neka druga mjenjačnica. Većina mjenjačnica ne podržava direktnu kupovinu LTCa, već je potrebno ući preko BTC ili Eth. Zatim se ulazna valuta šalje na neku burzu koja nudi usluge razmjene za LTC poput Bittrex, Bitstamp, Binance, itd.


Nakon što ste nabavili Litecoin, potrebno ga je spremiti na sigurno. Zapamtite: kriptovaluta koju držite na mjenjačnici nikad nije sigurna. Sigurna je jedino ako je privatni ključ vašeg [novčanika][wallet] u vašim rukama.

## Spremanje Litecoina

Postoji više načina za spremanje Litecoina.

### Papirnati novčanik

Kao što smo to opisali u [ovom članku][paper], papirnati novčanik je sasvim solidna opcija. Generirajte adresu na nekoj od sigurnih stranica poput https://liteaddress.org/, isprintajte svoj "novčanik", i sakrijte ga na sigurno. Javni dio adrese (označen lijevo sa SHARE na slici dolje) slobodno javno koristite - on služi za provjeru stanja, ili za slanje LTCa na tu adresu.

![A Litecoin wallet](https://bitfalls.com/wp-content/uploads/2017/12/01.png)

Na taj javni dio adrese *povucite* (withdraw) LTC s burze na kojoj ste ga kupili. Ako ste ga kupili [od nas][buycc], ovaj dio će biti riješen za vas - samo nam pošaljite lijevi kod prilikom narudžbe (na slici ovo što počinje s "LczA...").

Nakon slanja na adresu, vaš LTC je na sigurnom - samo isprintajte i sakrijte papir i obrišite datoteku s računala ako ste je spremili.

### Hardverski novčanik

Najsigurnija opcija je definitivno [hardverski novčanik][hw]. Svakako preporučamo da pročitate članak kako biste saznali koje prednosti nudi.

Evo kako podesiti [Ledger Nano S][ledger] za primanje Litecoina:

- Ako još niste, aktivirajte svoj Nano S spajanjem na USB port računala. Ukoliko je to njegovo prvo podešavanje, izbaciti će 24 riječi koje morate obavezno zapisati na papirić koji dolazi s uređajem, i spremiti na sigurno.

- Nakon što je uređaj u funkciji i podesili ste PIN, potrebno je instalirati Litecoin aplikaciju. Preuzimte službeni [App Manager][manager] kojim možete ažurirati uređaj i instalirati nove novčanike. Spojite uređaj na računalo, ukucajte PIN, pokrenite preuzetu app manager aplikaciju, te instalirajte Litecoin aplikaciju iz ponuđenog popisa. Ako je potrebno, ažurirajte uređaj.

  ![Ledger Manager](https://bitfalls.com/wp-content/uploads/2017/12/Screenshot-2017-12-13-16.34.22.png)

- Nakon instalacije Litecoin aplikacije, instalirajte [Litecoin aplikaciju za računalo][ltcapp].

- Na Ledger uređaju navigirajte do Litecoin walleta te uđite u njega. Otvorite aplikaciju na računalu. Ako vas aplikacija na računalu pita za odabir Legacy / Segwit, odaberite Segwit. 

  ![Segwit](https://bitfalls.com/wp-content/uploads/2017/12/03-1.png)

- Aplikacija koja je otvorena na računalu trebala bi automatski reagirati i prikazati podatke, uključujući mogućnost prikaza adrese na koju se valute mogu poslati (*Receive*). Na tu adresu povucite (*withdraw*) sredstva s burze na kojoj ste kupili LTC. Nakon što stignu, vaši Litecoini su na sigurnom.

  ![Wallet otvoren](https://bitfalls.com/wp-content/uploads/2017/12/04.png)

Bitno je biti svjestan čestih zabluda oko hardverskih novčanika - više o tome [ovdje][miscon].

**Napomena**: Coinbase još nije ugradio Segwit u svoj sustav, pa bi im adresa za Litecoin koja počinje slovom M mogla smetati (njihovo sučelje će vam to na vrijeme priopćiti). Da se takva situacija izbjegne, umjesto da generirate Legacy (L) adresu (što je isto OK rješenje za taj problem), pretvorite svoju M adresu u 3 adresu [ovim alatom](https://litecoin-project.github.io/p2sh-convert/) - jednostavno unesite M adresu i dobiti ćete ekvivalentnu 3 adresu:

![M to 3](https://bitfalls.com/wp-content/uploads/2017/12/05.png)

Tada slobodno šaljite LTC sa Coinbase na ovu "3EPJ..." adresu - obje adrese vode na istu destinaciju: vaš Ledger.

### Ostalo

Moguće je i držati LTC na raznim burzama, no to se ne preporuča. Ne postoji burza koja je prevelika da nestane bez traga. Do sada ih je nestalo preko 35, a preko noći je nestao i Mt. Gox - burza koja je na vrhuncu procesuirala preko 80% svih Bitcoin transakcija na svijetu. 

Što se hardverskih novčanika tiče, još jedan dobar izbor je [Trezor].

## Slanje Litecoina

### Ledger

Ovaj put je Ledger jednostavnija opcija - jednostavno otvorite aplikaciju kao i kod spremanja Litecoina, samo ovaj puta pritisnite opciju Send. Nakon unosa adrese i iznosa, potvrdite transakciju - jednom u sučelju, drugi put na samom uređaju kad vas upita za isto:

![Slanje LTCa preko Ledgera](https://bitfalls.com/wp-content/uploads/2017/12/06.png)

U prozorčiću možete odabrati brzinu slanja (brže je skuplje) i vidjeti procjenu troškova.

### Paper wallet

Slanje s papirnatog novčanika je malo teže. Kao što smo to objasnili u [uvodu u slanje i primanje Bitcoina][startbtc], postoje dvije metode: import i sweep.

Import znači da se samo privatni ključ učita u neki softver koji tada taj privatni ključ koristi za slanje LTCa dalje. Sweep znači da se LTC doslovno u cijelosti pošalje s papirnatog novčanika na novu adresu a stara postaje beskorisna, kao i njen ključ. Obje metode imaju isti ishod, samo je potonja malo sporija i skuplja (zahtjeva transakciju), ali sigurnija.

Postoji mnoštvo novčanika koji podržavaju učitavanje privatnog ključa i/ili sweep. Evo nekih:

- [Jaxx.io](http://jaxx.io)
- [Electrum-LTC](https://electrum-ltc.org/)

Instalirajte neki od njih na odgovarajući sustav / uređaj, skrenirajte QR kod svog privatnog ključa (ili ga ručno utipkajte), i vaša će sredstva biti spremna za slanje. Ako ste radili import umjesto sweep, najbolje bi bilo pospremiti papirnati novčanik na sigurno dok ne pošaljete cijeli iznos dalje, ili uništiti papir. Evo pune procedure slanja s papirnatog novčanika popraćene slikama. Koristili smo Electrum-LTC:

1. Ako prvi puta pokrećete Electrum-LTC, odaberite Auto-connect na prvom upitu
2. Na drugom ekranu pitati će vas za ime datoteke u koju da spremi vaš [wallet]. Ostavite na tvorničkim postavkama, ili po volji promijenite lokaciju. Samo zapamtite kamo ste datoteku spremili - gubitak te datoteke znači gubitak walleta.
3. Na sljedećem ekranu odaberite Standard Wallet.
4. Na sljedećem ekranu odaberite "Use public or private keys" za svrhu učitavanja našeg papirnatog novčanika. Ekran koji slijedi omogućiti će učitavanje privatnog ključa iz datoteke, QR koda, ili ručnim upisom:

![Import key](https://bitfalls.com/wp-content/uploads/2017/12/07.png)

Nakon unosa privatnog ključa, aplikacija će vas pitati za šifru kojom ćete dodatno enkriptirati i osigurati datoteku koja će sadržavati vaš novčanik. Nije obavezno, ali preporučljivo zbog sigurnosti.

Konačno, nakon ovog koraka, biti će vidljivo stanje računa s kojeg ćete moći i slati LTC:

![LTC history](https://bitfalls.com/wp-content/uploads/2017/12/08.png)

Otvorite ekran "Send", unesite destinacijsku adresu i iznos, podesite brzinu transakcije, po želji dodajte opis transakcije, i pritisnite "Send". Vaš LTC je na putu.

## Zaključak

Litecoin je relativno jeftina kriptovaluta s bistrom budućnosti - ne zbog tehnologije, već zbog reputacije "srebra" koju uživa prema Bitcoinovom "zlatu". Zbog te prepoznatljivosti a ujedno i zbog brže i jeftinije obrade transakcija, Litecoin bi mogao ozbiljno zaprijetiti Bitcoinu i Bitcoin Cashu - možda ne monetarnom vrijednošću, ali kao transakcijsko sredstvo svakako.

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[forks]: https://bitfalls.com/hr/2017/11/07/segwit2x-fork-can-expect-whos-behind/
[block]: https://bitfalls.com/hr/glossary/#block
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[mining]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[l3]: https://shop.bitmain.com/antminer_l3_litecoin_asic_scrypt_miner.htm
[cb]: https://www.coinbase.com/join/542b0423734ab06764000001
[buycc]: https://bitfalls.com/hr/how-to-buy-cryptocurrency/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[folio]: https://bitfalls.com/hr/portfolio-management/
[bitstamp]: https://bitstamp.net
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[paper]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[trezor]: https://trezor.io/
[hw]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[ledger]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[manager]: https://www.ledgerwallet.com/apps/manager
[miscon]: https://bitfalls.com/hr/2017/10/21/2-common-misconceptions-hardware-wallets/
[ltcapp]: https://chrome.google.com/webstore/detail/ledger-wallet-bitcoin/kkdpmhnladdopljabkgpacgpliggeeaf
[startbtc]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/