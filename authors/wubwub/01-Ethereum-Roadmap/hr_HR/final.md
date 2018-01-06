[Ethereum] projekt, iako pun potencijala,  još je u povojima. Dvije godine stara kriptovaluta i dalje tehnološki napreduje zahvaljujući njezinom kreatoru Vitaliku Buterinu i timu developera. Dobra vijest je da ne planiraju stati uskoro.

Sam Ethereum projekt je podijeljen u četiri faze razvoja:

  1. Frontier
  2. Homestead (Trenutna faza)
  3. Metropolis
  4. Serenity

## Frontier

Frontier je prva faza razvoja Ethereum mreže, lansirana u srpnju 2015. godine.
Namijenjena je prvenstveno ljudima s tehničkom pozadinom s obzirom na to da je interakcija s mrežom u potpunosti bila preko terminala (sučelja s kojim mnogi nisu upoznati).

 Frontier je sastavljen od osnovnih dijelova potrebnih za funkciju mreže u svrhu učenja okruženja, testiranja i razvoja decentraliziranih aplikacija, različitih alata i za početak rudarenja Ethera.

## Homestead

Homestead je druga i trenutna faza razvoja Ethereum mreže, lansirana 14. ožujka 2016. (Pi dan), aktiviran na 1,150,000 bloku i donosi mnogo poboljšanja protokola koji omogućuju daljnja nadograđivanja mreže i ubrzavanje transakcija.

## Metropolis

Treća faza Ethereuma je vrlo zanimljiva i donosi mnogo promjena i novotarija: sigurnosna  poboljšanja, pametni ugovori će postati još pametniji i moći će se dodatno automatizirati, Metropolis također olakšava prosječnom korisniku korištenje Ethereuma s light klijentima (programima koji ne trebaju preuzeti cijeli blockchain, koji se može mjeriti u stotinama gigabajta) kao što je [Status] za iOS i Android uređaje.

### Ledeno doba

Takozvano "Ledeno doba" je inicijativa koja će s vremenom onemogućiti klasično rudarenje s grafičkim karticama u Proof of Work (PoW) konsenzusu s namjerom prelaska na puno ekonomičniji Proof of Stake (PoS) konsenzus. 

*Proof of Stake bit će objašnjen u Serenity dijelu*

Poučeni uzorom zastoja razvoja Bitcoina upravo zbog ne slaganja rudara i core developera (skupine programera koji rade na glavnom protokolu bitcoina) je dovela do dvogodišnjeg prepucavanja o poboljšanju skalabilnosti i propusnosti tog [blockchaina][blockchain].

U međuvremenu su naknade za transakcije na Bitcoin mreži narasle na nečuvene razmjere od $5 pa čak i $100, ovisno o trenutnom prometu na mreži.

Ethereum developeri su implementirali _Ledeno doba_ tako da ljudi nemaju izbora nego prihvatiti prijelaz na PoS konsenzus, u prijevodu rudari ne mogu držati projekt kao taoca i zadržavati napredak zbog vlastitog profita kao što je bio slučaj s Bitcoinom.

Ledeno doba s vremenom povećava težinu rudarenja i usporava nastajanje blokova dok na kraju mreža ne bude potpuno zamrznuta i neupotrebljiva.

S _metropolisom_ se početak _Ledenog doba_ odgađa za 18 mjeseci, te se nagrada po bloku za rudare smanjuje s 5 Ethera svakih ~20 sekundi (koliko treba za svaki blok) na 3 Ethera po bloku, kao priprema za prijelaz na PoS gdje će se nagrada još smanjiti.

### ZK-Snarks

ZK-Snarks (Zero Knowledge proof) je tehnologija preuzeta s kriptovalute Zcash.
Ta tehnologija omogućava da verificiramo točnost transakcije bez da je mi sami obradimo, tako da ne znamo što je točno u toj transakciji, ali znamo da je transakcija točna, to jest legitimna. Drugim riječima, ZK-Snarks nam omogućuju anonimne transakcije na Ethereumu. Konkretno, princip _zero knowledge_ (nula znanja) se opisuje kao "Znam da se nešto desilo, i mogu dokazati da se nešto desilo, ali ne znam što."

 ![Eth_Zcash](https://bitfalls.com/wp-content/uploads/2017/10/Eth_Zcash-2.png)

Budući da je Ethereum javno dostupan blockchain, tvrtke koje žele implementirati Ethereum blockchain u svoje poslovanje se boje na blockchain plasirati potencijalne osjetljive i povjerljive podatke. U ovom slučaju, ZK-Snarks olakšavaju održavanje tajnosti povjerljivih podataka.

### Byzantium i Constantinople

Metropolis nadogradnja će se razdvojiti u dva stadija , to jest dvije zasebne nadogradnje nazvane Byzantium i Constantinople.

Prva nadogradnja _Byzantium_ sadrži EIP-ove (Ethereum Improvement Proposal - Prijedlog za poboljšanje Ethereum protokola) 100, 140, 196, 197, 198, 211, 214, 649 i 658. Dok Constantinople donosi EIP 86 i 96.

[Ovdje možete detaljnije proučiti  što svaki EIP radi][eips]

Byzantium se trenutno testira na Ropsten testnoj mreži, smatra se da će testni period trajati 2-4 tjedna, a ako sve bude u redu, na glavnoj mreži ga možemo očekivati negdje krajem listopada 2017.

## Serenity

### Casper Proof of Stake
                                
Zadnja planirana Ethereum nadogradnja _Serenity_ nam donosi dugo očekivani Proof of Stake konsenzus. Glavna razlika između PoW i PoS algoritma je u tome što PoW algoritam koristi moćan hardver  koji računa [hash blokova][hash] i tako validiraju blokove i transakcije. Kao što ime kaže, Proof of Work (Dokaz Rada), strojevi ulože vrijeme i rad da bi došli do pravog hasha.

U Proof of Stake je rudarenje virtualno. Validator (onaj tko potvrđuje validnost transakcija [pečaćenjem blokova][blockchain]) na blockchain šalje posebnu transakciju koja će zaključati njegov Ether na određeno vrijeme. Možemo to smatrati kao oročenje u banci, na koje validatori dobivaju dividende. 

Validatori se esencijalno klade koji će blok ući u blockchain. Ako validatori poštuju pravila protokola i uključuju legitimne transakcije u blokove, validatori će dobiti dividende.

U slučaju da validator želi uključiti nelegitimne transakcije u blok, taj validator gubi oročeni Ether, tako da svaki pokušaj varanja košta.

### Po čemu je PoS zapravo bolji od PoW algoritma?

* Nema potrebe za trošenjem velike količine struje. Procjenjuje se da rudarenje Bitcoina i Ethereuma dnevno potroši preko milijun dolara struje i hardvera po danu.

* Zbog puno manje potrošene struje, može se smanjiti inflacija tako da smanjimo izdavanje novih coina i stvorimo ravnotežu između novostvorenih coina i coina koji su tijekom vremena izgubljeni i uništeni, to jest možemo imati [deflaciju][defl].

* PoS se bori protiv centralizacije rudara kakvu sad vidimo s Bitcoinom u Kini. Također, PoS sprječava rudare da naštete mreži, što smo također nedavno vidjeli na Bitcoinu.

* 51% napadi u kojima napadač pokušava preuzeti mrežu imajući 51% snage mreže, postaju enormno skuplji nego u PoW algoritmu, pošto napadač mora posjedovati 51%  valute u cirkulaciji među validatorima. Ako potencijalni napadač stvarno ima toliko novaca, isplativije bi bilo da ode u prijevremenu mirovinu i zaboravi na sve. U protivnom bi te sve novce lako mogao izgubiti.


### Sharding

Svaki blockchain ima istu slabost, a to je skalabilnost. Kad blockchain dođe do točke zasićenja gdje ima više transakcija nego mreža može procesirati, brzina kojom se transakcije izvršavaju se smanjuje, nešto kao kad se cesta suzi s 4 trake na 2 trake.

Kako se automobili na cesti gužvaju u 2 trake, tako transakcije ne mogu stati u blok i moraju čekati svoj red, no još jedan problem koji se ovdje javlja je taj što tko plati veću naknadu za transakciju, njegova transakcija ima i veći prioritet. To znači ne samo da se mreža uspori zbog puno transakcija, nego i naknade za transakcije rastu. 

*Za usporedbu, Bitcoin može procesuirati ~3-7 transakcija po sekundi, dok Ethereum može procesuirati ~7-15*

Osnova ideja Shardinga je da blockchain rastavimo na puno manjih dijelova, takozvanih "Shardova" ("krhotina").

Primjer shardinga na Ethereumu, sve adrese koje počinju s 0x00 stavimo u jedan shard, sve adrese koje počinju s 0x001 stavimo u drugi shard i tako dalje.
Ovaj način omogućuje da se transakcije obrađuju paralelno umjesto serijski.

Da pojasnimo: trenutno u blockchainu svaki čvor (sudionik mreže koji rudari) mora sinkronizirati čitavu mrežu počevši od izvornog bloka. Kako redom sinkronizira blokove, čvor ponovno izvršava i provjerava sve transakcije koje su se ikad dogodile na blockchainu i uvjerava se da su legitimne.

U shardingu svi čvorovi u jednom shardu verificiraju samo taj shard, u drugom shardu njegovi čvorovi  verificiraju taj shard, i tako dalje.

Ovo nam omogućuje ubrzanje transakcija na mreži jer čvorovi više ne moraju verificirati cijeli blockchain, nego samo dio njega, ovisno kojem shardu pripada. Naravno, to će također imati utjecaja i na sami prostor na disku koji čvor zahtjeva.

Sharding sustav je još uvijek u razvoju, očekujemo njegovu implementaciju zajedno s Casperom u Serenity nadogradnji.

## Raiden Network

Raiden mreža je off-chain rješenje za povećavanje skalabilnosti na Ethereumu.
Off-chain znači da je Raiden infrastruktura građena na Ethereumu, ali nije povezana s njegovim blockchainom. Raiden donosi gotovo instantne prijenose [ERC20 tokena] bez uobičajene potrebe za globalnim blockchain konsenzusom. Ovo je moguće pomoću digitalno potpisanih transfera zvanih **balance proofs**.

Raiden funkcionira tako da se između dvije osobe otvori "platni kanal" koji omogućava platni promet u oba smjera s vrlo malim naknadama.

Nakon što se platni kanal otvori, potrebno je napraviti depozit tokena s kojim želite trgovati.

Recimo da Marko i Pero svatko ima na platnom kanalu 200 tokena.

Marko pošalje 150 tokena za uslugu Peri, platni kanal to zabilježi i Pero sada ima 350 tokena.

Pero pošalje 25 tokena Marku za neku uslugu, platni kanal to zabilježi i Pero sada ima 325 tokena, a Marko ima 75 tokena.

Marko opet šalje 50 tokena Peri za neku uslugu, a Pero zatim šalje Marku 100 tokena za neku uslugu,  zbog jednostavnosti primjera pretpostavit ćemo da je njihovo poslovanje završeno i oni zatvaraju platni kanal.

Platni kanal tada izračuna razliku i na blockchain se šalju samo dvije transakcije::

Pero je Marku poslao: 125 tokena.

Marko je Peri poslao: 200 tokena..

Stanje na kraju:

Pero ima: 275 tokena.

Marko ima: 125 tokena.

Platni kanali su korisni kad se koriste mikrotransakcije, umjesto da se na blockchain šalju stotine transakcija od npr. 20 lipa, plaćanje naknade za svaku transakciju i čekanje da se svaka transakcija uključi u blok, otvori se platni kanal u kojem se transakcije izvrše gotovo trenutno i na kraju se sve pošalje u jednoj transakciji na blockchainu.

## Zaključak

Ethereum ima još puno toga ispred sebe i trebat će još godine rada da se dođe do završenog proizvoda. No cijeli kripto prostor je još uvijek u povojima i očekuju nas još velike stvari kako blockchain tehnologija bude napredovala. Blockchain je poremetio puno industrija koje su funkcionirale na zastarjelim principima, a ovo je samo početak novog poglavlja povijesti.







[Ethereum]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/

[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/

[hash]: https://bitfalls.com/hr/glossary/#hash
[Status]: https://status.im
[defl]: https://bitfalls.com/hr/glossary/#deflation
[eips]: https://github.com/ethereum/EIPs#deferred-eips-adoption-postponed

[ERC20 tokena]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
