Što je to _blockchain_? 

Kako funkcionira, zašto je popularan, i zašto će (prema nekima) revolucionizirati svijet? 

U ovom ćemo članku objasniti blockchain tehnologiju na relativno banalnom primjeru koji vrijedi za većinu kriptovaluta. Niste upoznati s kriptovalutama? Uvod [ovdje][cryptocurrencies]!

## Mario i Luigi

Mario treba poslati $100 svom bratu, Luigiju, jer Luigi kakav jest, opet je upao u dugove na drugom kraju svijeta.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-01.png" alt="Luigi u dugovima" width="350">

Mario ulazi u banku i kaže "Poslao bih $100, primatelj je Luigi." - na to mu službenik kaže "Bankovnu karticu, molim", "Osobnu, molim" i "Riješeno" - tim redom.


<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-02.png" alt="Mario šalje novac bankom" width="350">

U ovom *centraliziranom* scenariju, banka je **_centralni_** autoritet nad novcem kojim barataju Mario i Luigi. I Mario i Luigi vjeruju banci da je iznos koji oni vide na svom računu i prije i poslije transakcije istinit. 

Drugim riječima, kada Mario daje $100, a Luigi primi $100, oni vjeruju da se ta vrijednost stvarno pomakla jer im banka to garantira, unatoč tome što jedino što banka mora učiniti je promijeniti jednu vrijednost u bazi podataka - sve je digitalno.

No, kada ovisimo o nekom centralnom autoritetu, dovoljno je da taj autoritert bude korumpiran (nestane zajedno s novcem, postane zao i ne ukuca vrijednost kod Luigija, ali smanji vrijednost kod Maria te zadrži iznos ili bude nespretan i ukuca krivu vrijednost...) i naše financije su ugrožene.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-03.png" alt="Lopov krade novac iz banke" width="450">

Jedan način osiguranja od takvih situacija je da preskočimo banku i imamo sustav gdje sami upravljamo svojim financijama. 

Zamislite komad papira na kojem bilježimo stanje računa. No, ako se radi o sustavu koji koriste samo Mario i Luigi tako da ručno označe jedan +$100, a drugi -$100 svaki na svom papiru, teško će doći do dogovora ako jedan postane pohlepan. Zato je za takvu *distribuiranu* (moglo bi se reći ne-*centraliziranu*) metodu potrebno imati *dovoljno ljudi koji su zainteresirani za takav sustav* (minimalno troje).

## Papiri

Recimo da imamo 5 članova: Yoshi, Mario, Luigi, Wario, i Bowser, te svatko ima svoj komad papira.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-04.png" alt="Svatko ima svoj komad papira" width="550">

Mario želi poslati $100 Luigiju. Da bi to učinio, Mario svima objavi (glasno vičući): Šaljem $100 Luigiju, molim zabilježite!"

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-05.png" alt="Mario šalje novac Luigiju" width="550">

U tom momentu svatko provjerava ima li Mario dovoljno novca na svom računu (da, stanje svakog računa je javno), i ako ima, na svoj komad papira zapišu taj prijenos. Ti se prijenosi (_transakcije_) nižu sve dok našim zapisničarima ne ponestane mjesta na papiru. Drugim riječima, **svaka** transakcija koja se obavi između **bilo koga** biva zapisana na **svačijem** papiru.

Prije nego popunjeni papir stavimo u fascikl i uzmemo novi, treba ga potpisati posebnom šifrom - tj. zapečatiti. 

## Pečati i rudarenja

Taj pečat, tj. šifra, garantira da je sadržaj koji je do tada napisan istinit. 

Kako dolazimo do te šifre? Posebnim algoritmom (matematičkom operacijom) koji, kada u njega ubacimo određene podatke, izbacuje uvijek istu šifru ako su ulazni podaci isti.

Uzmimo za primjer sljedeći algoritam:

X1 + X2 + ... Xn = Z.

Drugim riječima, obično zbrajanje. Pretpostavimo da se vrijednosti našeg papira smatraju istinitima (dakle prijenosi novca smatraju se važećima i potvrđenima) ako je zbroj (šifra) 10000.

1000 + 6000 + 3000 = 10000.

U ovom slučaju, ulazni podaci su 1000, 6000, i 3000, a šifra je 10000. 

Pretpostavimo dakle da je među našim zapisničarima aktivan dogovor da kada zbrojimo sve brojke napisane na papiru **i specifičnu** kombinaciju drugih brojeva, a da time dobijemo 10000, vrijedi kao potvrda da su podaci na papiru istiniti.

Primjerice, ako na papiru imamo zapisanih sljedećih 5 transakcija:

- Mario -> Luigi = 100
- Bowser -> Yoshi = 200
- Yoshi -> Luigi = 100
- Mario -> Yoshi = 500
- Luigi -> Wario = 100

Zbroj je 1000, dakle tražimo kombinaciju koja zajedno s 1000 daje 10000. Preostalih 9000 možemo dobiti raznim kombinacijama:

- 5000 + 4000
- 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000
- 2000 + 3000 + 2000 + 2000
- itd...

Računalo ne zna intuitivno zaključiti koji ulazni podaci će dati zbroj od 10000. Da bi dobilo zbroj od 10000 računalo mora nasumično birati brojeve manje od 10000 tako dugo dok ne pogodi kombinaciju koja daje 10000. Dakle, od naših zapisničara, onaj tko prvi nasumično pogodi kombinaciju koja daje 10000 svima obznanjuje isto. 

Recimo da je Yoshi našao kombinaciju 4000 + 5000. On svima kaže: "Imam desetku! Provjerite 4000 i 5000!". Budući da je vrlo lako provjeriti istinitost te tvrdnje samo uvrštavanjem brojki u naš algoritam, drugi zapisničari ukucaju Yoshi-eve brojke u računice svojih papira i stvarno - izlazi broj 10000.

Svi papiri na kojima algoritam zaista daje 10000 smatraju se važećima, te se spremaju u fascikle. Ako na nečijem papiru dodavanje 4000 i 5000 originalnom zbroju ne daje 10000 (jer je, primjerice, Bowser napisao da je Yoshiju dao 400 a ne 200), znači da papir ima grešku - namjernu ili slučajnu. 

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-07.png" alt="Svi osim Bowsera daju potvrdni rezultat na provjeru" width="550">

U tom slučaju, Bowserov papir smatra se nevažećim, i ukoliko on želi i dalje koristiti ovaj sustav, mora baciti svoj papir, prepisati podatke s nečijeg kako bi i on imao zbroj od 10000, i obećati da će ubuduće biti pažljiviji. Yoshi, koji je našao dobitnu kombinaciju, dobiva nagradu u visini od npr. $5 od "sustava", tj. od nikoga - sustav proizvede novih $5 koji idu Yoshiju kao nagrada. 

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png" alt="Yoshi prima nagradu, Bowser baca svoj papir" width="550">

Ta *proizvodnja* se u svijetu kriptovaluta zove *mining* ili *rudarenje*.

Ovo je bio drastično pojednostavljeni primjer, no jedino po čemu se stvarni sustav blockchaina razlikuje (osim toga da je u stvarnosti sve digitalno i automatizirano) je algoritam koji se koristi. Tu se radi o malo kompleksnijem algoritmu koji može primati i slova i ostale znakove, i izbacuje šifre poput sljedećih: `90bdaa79bbccacf8558edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`. 

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-06.png" alt="Zapećaćen papir" width="350">

Ovakve šifre zovu se *hash*-evi, i algoritmi koji ih proizvode, poput SHA256 algoritma, zovu se *hashing funkcije*. Probajte otvoriti [ovu poveznicu](http://www.xorbin.com/tools/sha256-hash-calculator) i unesite bilo koju količinu podataka u polje: bez obzira na to koliko podataka unesete (bila to jedna riječ ili cijeli sadržaj biblije), rezultat će uvijek biti *hash* od samo 64 znaka.

Stoga, da bismo dobili šifru za naš komad papira, u algoritam ubacujemo sve transakcije napisane na papiru, i one postaju jedan hash. Budući da postoji beskonačno mnogo kombinacija brojki i slova i njihovih redoslijeda koje možemo poslati kao ulazne podatke, pogoditi izvorni set podataka samo iz izlazne šifre je matematički nemoguće.

Specifično, u Bitcoin blockchainu dogovor je da je pojedini *papir* važeći, ako šifra (koju dobijemo iz algoritma nakon što ubacimo *šifru prijašnjeg papira* i neku nasumičnu kombinaciju brojki i slova) počinje s nulama. Na primjer, ako papir 1 ima hash `0000000000000000058edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`, šifra sljedećeg će biti ona koja kada je pridodamo prošloj daje novi hash koji počinje s određenim brojem nula.

Da bi računalo našlo tu kombinaciju koja nam je potrebna za generiranje nove šifre, ono mora pogađati. Moderna računala su vrlo brza, i s lakoćom isprobavaju tisuće kombinacija na sekundu, no to još uvijek nije dovoljno brzo budući da je potencijalnih kombinacija beskonačno mnogo. Iz primjera gore vidimo da je *kompliciranost pogađanja* 17, jer je na početku hasha 17 nula. Novi hash stoga mora imati 17 ili više nula. S vremenom se broj nula u hashu povećava, te će rudariti u budućnosti biti sve teže i teže.

Kada se papir svakog sudionika na taj način ovjeri kao *važeći*, on se stavlja u fascikl i uzima se novi, prazni, na koji se pišu nove transakcije.

### U Prijevodu

U prijevodu na blockchain jezik, jedan papir je *block*. 

Jedan block sastoji se od mnoštva *transakcija*. 

Više blockova nižu se jedan za drugim, i čine *blockchain* (lanac blockova), ili _ledger_ (knjigu zapisa). 

Računala koja pogađaju kombinacije kako bi otkrila hasheve zovu se _node_-ovi (čvorišta, tj. jezgre). Node koji je pogodio ciljanu kombinaciju dobiva nagradu u visini nekoliko tokena, tj. u ovom primjeru Bitcoina. 

Ovo pogađanje zove se *mining* ili *rudarenje*, jer "kopamo" nove kriptovalute iz "ničega", koristeći struju i vrijeme za pokretanje računala. Naši su likovi iz priče u vozilima upravo zato jer se utrkuju - onaj tko prvi otkrije dobitnu kombinaciju ujedno dobiva i nagradu od sustava za rješenje iste. Tako i u blockchain svijetu brže računalo (najčešće) znači i veće i češće profite.

Samo postojanje nove važeće šifre smatra se **dokazom odrađenog posla** ili **proof of work**. Trenutno, većina kriptovaluta koristi **proof of work** kako bi učinile varanje i prelako pogađanje financijski neisplativim zbog visokih računa struje i utrošenog vremena. Neki protokoli poput Ethereuma prelaze na **proof of stake** (dokaz uloga), sustav u kojem se minimizira besmislena potrošnja struje, ali pojačava kazna za one ulagače koji rade protiv sustava. Više o tome u posebnom članku uskoro.


## Zaključak

Sve kriptovalute baziraju se na _blockchainu_. Blockchain je ono što im omogućava da budu transparentne, definitivine (nemoguće za falsificirati ili duplicirati) i donekle konačne (ograničene u količini). Za razliku od fiat valuta (HRK, Euro, USD, itd.), kriptovalute nije moguće jednostavno naštampati - čak ni ako ste njihov izumitelj (osim u slučaju nekih lažnih kriptovaluta poput Ripple (XRP) i Onecoin - više o njima neki drugi put).

Blockchain omogućava distrubuiranu kontrolu nad financijama i izbjegavanje posrednika i to je jedan od ključnih razloga za veliki uspjeh [kriptovaluta][cryptocurrencies]. Zbog distribuirane naravi blockchaina i miljuna korisnika diljem svijeta od kojih svi služe kao "zapisničari", mnogi kriptovalute smatraju neuništivima i nezaustavljivima - no to baš i nije tako (vidi poveznice u sljedećem dijelu).

## Kamo dalje?

- [Što su kriptovalute][cryptocurrencies] da biste saznali o čemu se tu zapravo radi
- [Bitcoin nije nezaustavljiv][unstoppable] da biste saznali koliko je zapravo lako zaustaviti kriptovalute
- [Bitcoin nije konačan][finite] - da biste saznali zašto 21 miljun Bitcoina nije maksimum vrijednosti koju će ikada postići
- [Bitcoin nije anoniman][anon] - da biste saznali zašto se točno toliko često (netočno) govori da je Bitcoin anoniman i pogodan za "crno tržište"
- [Što je Ethereum?][eth] - da biste naučili osnovne stvari o najmoćnijoj kriptovaluti i sličnostima s Bitcoinom 

[cryptocurrencies]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[unstoppable]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[anon]: https://bitfalls.com/hr/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
