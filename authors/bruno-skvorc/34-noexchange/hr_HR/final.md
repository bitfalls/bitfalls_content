_Da biste razumjeli sadržaj iz ovog članka, preporučamo pročitati uvodne materijale:_

- _[Što su to kriptovalute][cc]_
- _[Što je to novčanik za kriptovalute][wallet]_
- _[Definicija privatnog ključa][privkey]_

---

Često kažemo da nije sigurno držati [kriptovalute][cc] na burzama na kojima su kupljene. No, zašto nije sigurno? I koji je [sigurniji način][paranoia] čuvanja kriptovaluta? Jesu li mobilni [walleti][wallet] išta sigurniji od onih na osobnim računalima? Jesu li bolji ili lošiji od [hardverskih novčanika][hw]? A od [paprinatih][paper]?

## Nesigurnost burzi i mjenjačnica

Vrlo je lako pasti u zamku držanja kupljenih kriptovaluta na mjestu na kojem su kupljene. Burze podržavaju više valuta odjednom, omogućavaju brzo reagiranje kada jednu treba zamijeniti za drugu zbog velikih tržišnih pomaka i obrađuju veliki broj transakcija orgomnih volumena, pa su **_preveliki da jednostavno nestanu_**.

Ovo zadnje je velika i opasna zabluda.

U momentu pada u 2014., Mt. Gox - najveća Bitcoin burza tada - je procesuirao 70% svih Bitcoin transakcija na svijetu. Jedna web stranica bila je odgovorna za većinu prometa kriptovalutama. Nestali su gotovo preko noći, zajedno s kriptovalutama svih klijenata. Takvih je incidenata od tada bilo [mnogo][exchangesgone], i svaki put se govorilo "ovaj put neće" i "preveliki su da padnu".

![Spaljen novac](https://bitfalls.com/wp-content/uploads/2018/01/01.jpg)

Kada su vaše kriptovalute na računu neke burze, oni imaju privatni ključ tog kripto-novčanika jer im je potreban kako bi mogli sredstva slati s istog. Ako oni imaju privatni ključ neke adrese, a vi ne, oni su pravi vlasnik tih kriptovaluta i vi im vjerujete na riječ da je ta količina kriptovalute na vašem računu.

Jedini način da imate potpunu kontrolu nad svojim kriptovalutama je da imate privatni ključ vašeg novčanika u svojim rukama i da ne dopustite da ga se itko drugi dočepa.

No... kako do vlastitog privatnog ključa?

## Vlastiti novčanici

Postoje dvije glavne kategorije novčanika koji će vam omogućiti kontrolu nad svojim privatnim ključem: softverski i hardverski.

### Softverski

Softverski novčanici su programi koje preuzimate na svoj mobilni uređaj ili osobno računalo. Postoji ih više stotina, i po nekoliko desetaka za pojedinu kriptovalutu, ovisno o valuti.

Ti se novčanici dijele u dvije pod-kategorije: "light" (lagani) i "full" (puni). Zovemo ih i "klijentima" - softverski naziv za program koji se spaja na neki protokol ili mrežu. Npr. Outlook je "email klijent" jer je to softver kojim koristimo email protokol.

Full klijenti s mreže preuzimaju cijeli [blockchain][bc]. To im omogućava da odmah primjete promjene na blockchainu i detektiraju nadolazeće transakcije ali i da ih s lakoćom šalju u mrežu te da validiraju transakcije iz prošlosti. Full novčanici zahtjevaju puno diskovnog prostora (stotine gigabajta) pa ih obično koriste samo ozbiljni korisnici i česti primatelji transakcija poput dućana, webshop softvera, itd. Primjer full klijenta je [Bitcoin Core][bitcore] softver:

![Bitcoin Core softver](https://bitfalls.com/wp-content/uploads/2018/01/02.png)

Light klijenti komuniciraju s mrežom i pitaju full novčanike s kojima su spojeni za informacije koje su im potrebne. Tako primjerice ako neki light novčanik treba provjeriti je li neka transakcija iz prošlosti validna, on pita najbliže full novčanike za tu informaciju. Light novčanici su maleni i mogu se koristiti na mobilnim uređajima i starijim osobnim računalima bez problema. Light klijenti ne moraju biti softver koji se trajno instalirava na računalo ili uređaj - mogu biti i web stranice poput [MyEtherWallet][mew]. Jedan od primjera kvalitetnih light klijenata za Bitcoin je [Electrum][electrum].

#### Problem s Mobilnim Walletima

Pristupajte light klijentima (novčanicima) koji se preuzimaju na mobilne uređaje pažljivo.

Mobilni novčanici često preuzimaju brigu o privatnom ključu za vas kao i neka centralizirana burza. U tom slučaju, ako serveri tog novčanika budu kompromitirani ili se ugase zbog bilo kojeg razloga, nestaje i vaš pristup vašim kriptovalutama.


<img src="https://bitfalls.com/wp-content/uploads/2018/01/03.png" width="250" alt="Abra wallet">

_Na slici iznad je [Abra] - novčanik koji sprema vaše kriptovalute na serverima tvrtke Abra._

Ako i imate mobilni wallet koji vam dozvoljava ispis vašeg privatnog ključa i potpunu kontrolu nad njim, bitno je biti posebno pažljiv kod bilo kakve ne-trivijalne količine kriptovaluta na takvim novčanicima. Naime, na mobilnim operativnim sustavima - pogotovo onim otvorenima poput Androida - vrlo je lako naletjeti na lažnu aplikaciju u katalogu aplikacija. Ta će instalirati softver za njuškanje na vaš mobitel i javiti se na server s privatnim ključem čim se isti i jednom pojavi na ekranu iz bilo kojeg razloga. Kod otvorenih sustava poput Androida, i posebno ako je mobitel _rootan_ (otključan za administratorske mogućnosti), dovoljno je priključiti ga na jedan javni terminal za punjenje kakvih ima u zračnim lukama ili prošetati s privatnim ključem na ekranu ispred neke web kamere, i vaši su podaci ukradeni.

Mobilne uređaje se nikako ne bi smjelo smatrati sigurnima.

### Hardverski

Hardverski novčanici su oni koji na nekom fizičkom mediju koji nema dodira s internetom (pa ga time nitko ne može _hakirati_ ni preuzeti bez vašeg znanja) spremaju vaš privatni ključ. To može biti nešto poput [Ledgera][hw], ili [paprinati novčanik][paper]. Pročitajte sadržaj na poveznicama da naučite više o svakom tipu.

Svakako preporučamo [Ledger][ledgershop], no i papirnati novčanik je u redu ako je napravljen preko sigurne stranice poput [ColdStorage Tools][cst]. Isprintajte ga (ili još bolje - ugravirajte u metalnu pločicu), spremite u sef i osjećajte se sigurno.

## Zaključak

Jedini sigurni način čuvanja kriptovaluta je _cold storage_ - hladno spremanje. Drugim riječima, jedino mjesto na kojem su vaše kriptovalute sigurne je ono na kojem samo vi imate privatni ključ svog novčanika, i to na takav način da isti nema dodira s internetom.

Ukoliko vam kupnja hardverskog novčanika kao što je [Ledger][ledgershop] nije opcija, naš je prijedlog da si napravite papirnati novčanik za željenu kriptovalutu pomoću sigurnih alata na stranicama [ColdStorage Tools][cst].

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
[privkey]: https://bitfalls.com/hr/glossary/#private-key
[bitcore]: https://bitcoin.org/en/bitcoin-core/
[electrum]: https://electrum.org/#home
[Abra]: https://www.abra.com/