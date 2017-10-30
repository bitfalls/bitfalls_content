Segwit? Segwit2x? Fork? NYA agreement? Sve su to pojmovi koje ste možda čuli u proteklih nekoliko mjeseci, a možda ne znate što znače? U ovom članku ćemo Vam pojasniti spomenute pojmove i što se krije iza njih.

*Ako ste novak u kriptovalutama, da bi razumjeli problematiku ovoga, preporučujemo da pročitate [uvod u blockchain][blockchain].*


## Problematika

Svaki blockchain ima istu slabost, a to je skalabilnost. Kad blockchain dođe do točke zasićenja gdje ima više transakcija nego mreža može procesirati. Brzina kojom se transakcije izvršavaju se smanjuje, a time se naknada za transakcije povećava jer rudari u blockchain prvo uključuju transakcije s većom naknadom, a tek onda idu ostale.

Pojednostavnimo na primjeru:

Zamislimo da su blokovi kutije, u koje slažemo transakcije. 
Svakih deset minuta možemo napuniti jednu kutiju transakcijama. 
Za svaku transakciju koju smo stavili u kutiju, dobili smo 1kn, no broj transakcija se vrlo brzo povećao i više ne možemo sve transakcije staviti u kutiju.

Uzmimo sad ovaj scenarij, u kutiju stane još jedna transakcija za koju ćemo dobiti 1kn, no tada dođe druga transakcija koja nudi 2kn da ju stavimo u kutiju. Stavimo tu transakciju u kutiju i dobijemo 2kn za nju, no time smo izbacili ovu transakciju od 1kn.

Ovako smo dobili neželjeni učinak s kojim se ljudi međusobno natječu čija će transakcija imati prednost, odnosno tko će platiti veću naknadu.

Sad se vratimo 2 godine u prošlost kad je počela rasprava o skalabilnosti Bitcoina.
Popularnost Bitcoina je skočila, a s time i stopa transakcija.
Bitcoin nije mogao procesirati sve transakcije u očekivanom vremenu i gore navedeni scenarij je postao stvarnost.

Drugi problem koji se u međuvremenu pojavio je način "optimizacije" rudara po imenu [ASICBoost].

ASICBoost omogućava veću efektivnost rudarenja. Manja potrošnja električne energije po [GH/s (Gigahash/sekunda)][hash]. Kineski proizvođač opreme za rudarenje, Bitmain imao je ugrađen ASICBoost u rudare koje su oni koristili, a time su [zarađivali ~30% Bitcoina više][ABOOSTGregMax], što je otprilike do $100 milijuna USD godišnje.


## Rješenje

Tu se javljaju problemi jer imamo suprotstavljena dva kampa: 

1. Core developeri (programeri koji rade na Bitcoin protokolu)
2. Kineski rudari

### 1. Rješenje: 

**Core developeri** žele implementirati [Segregated Witness][SegWit] (SegWit u daljnjem tekstu), koje je kompleksnije rješenje, ali isplativije na duže staze. Također postavlja temelje za *Lightning network* koja će dodatno povećati skalabilnost s off-chain transakcijama. 

#### Lightning Network

Tehnologija je slična i ima istu namjenu kao [Raiden mreža][Raiden] na Ethereumu.
Ukratko, Lightning mreža pomoću pametnih ugovora i platnih kanala omogućuje masovni skok u transakcijama koje su prvotno off chain (nisu na blockchainu), time su omogućene i mikrotransakcije jer su transakcijske naknade ne postojeće, na kraju se sve pošalje na blockchain u jednoj transakciji za koju se plati naknada.

Za više detalja pogledajte [ovaj video][LightningNetwork]


## Što je SegWit

SegWit je tehnologija koja omogućava blockchainu povećavanje broja transakcija.
No, kako SegWit funkcionira?  

Bitcoin transakcija se sastoji od nekakvih informacija kao što su veličina transakcije, koliko ulaza i izlaza transakcija sadrži, kolika je naknada za rudare, kada je transakcija uključena u blok itd.

Ovdje je najbitniji dio da **svaka** transakcija mora biti **potpisana [privatnim ključem][privatekey]**. 
Upravo taj potpis zauzima većinu mjesta u transakciji, no bez tog potpisa ne znamo da li je transakcija valjana.

### Kako ovo može funkcionirati ako je potpis nešto na čemu se decentralizirana mreža temelji

Zamislite da putujete vlakom, u vagone ulaze putnici s prtljagom. Svi putujete jako daleko i svi nosite puno prtljage, tako da ste svi zbijeni jedan do drugoga i nema baš puno mjesta da se raskomotite.

Vlakovođa se sjetio da za svaki vagon zakači manji vagon u kojemu će biti spremljena prtljaga. Putnici sada imaju mjesta da se raskomote, a ako je potrebno, još putnika će se moći ukrcati.

**Vlak** je ovdje **blockchain**, **vagoni** su **blokovi**, **putnici** su **transakcije**, a **prtljaga** su **potpisi**.

Možemo reći da sam SegWit povećava veličinu bloka u praksi sa 1mb na 1.6mb - 2mb. (U teoriji do 4mb)

Što su ovdje developeri odlučili napraviti? Odlučili su "prepoloviti transakciju" i odvojiti **potpis** od **ostatka transakcije**, smanjivši veličinu transakcije su povećali kapacitet bloka, a čvorovi koji ne primaju SegWit potpise su i dalje na 1mb blokovima.

Čvorovi koji žele provjeriti legitimitet transakcija mogu zatražiti i potpise za svaku transakciju tako da imaju instaliran čvor koji podržava SegWit npr. Bitcoin Core. 


### 2. Rješenje:

Kineski rudari, s vlasnikom Bitmaina Jihanom Wu na čelu, zagovarali su povećanje blokova, s 1mb na čak 8mb. To naravno nije dugoročno rješenje, jer kako se Bitcoin bude sve više i više koristio, tako ćemo nakon nekog vremena opet imati ovakve probleme.

No, stvarni razlog zašto su se kineski rudari bunili je taj što SegWit **onemogućava ASICBoost**, a time ostaju bez velike prednosti.

####  U čemu je problem

Ako se veličina  blokova poveća na 8mb, tako drastično povećanje kapaciteta blokova bi negativno utjecalo na čvorove u mreži jer sada moraju pohraniti i obraditi 8 puta više podataka u istom vremenskom razdoblju.

Inicijalna sinkronizacija čvora će trajati puno duže (proces preuzimanja i validiranja cijelog blockchaina nakon instalacije Bitcoin softvera). 

Trebat će više resursa da se čvor održi, u smislu diskovnog prostora i internetske propusnosti.

S vremenom postoji mogućnost da zbog veličine blockchaina obični ljudi si neće moći priuštiti svoj čvor, nego će si to moći priuštiti samo veliki podatkovni centri i tvrtke, što će dovesti do centralizacije, a s time će Bitcoin postati korporativni talac. Onaj tko kontrolira čvorove, kontrolira i Bitcoin, zato je bitno da mogućnost vlastitog Bitcoin čvora ostane pristupačna svima.

Na primjer, ako dođe do centralizacije čvorova, oni koji ih kontroliraju mogu podiči limit s 21 milijun Bitcoina na koliko žele, mogu odbijati inače valjane transakcije, mogu mijenjati pravila protokola. To je vrlo opasno za Bitcoin, a i za ostatak kritpo prostora. 

*Zbog toga što je Bitcoin protokol zasnovan na principu ne povjerenja, potiče se da sami provjerimo istinitost transakcija na mreži tako da imamo vlastiti čvor.*


### 3. Rješenje:

Prvo aktivirati SegWit, a kasnije povećati blokove.

Rješenje se čini kao dobar kompromis, zar ne? 
Unatoč gore navedenim razlozima zašto to još trenutno nije dobar put za postizanje skalabilnosti, više je zabrinjavajuće tko gura SegWit2x i tko stoji iza toga.

## Pa krenimo

### NYA dogovor i SegWit2x

[New York Agreement][NYA] je dogovor između nekih od najvećih kompanija u Bitcoin prostoru i velikih rudara. Dogovoreno je da će se prvo aktivirati SegWit, a 90 dana poslije će se aktivirati SegWit2x koji će još podići veličinu bloka na teoretskih 8mb.
Cijeli razvoj Segwit2x je nadgledan od strane Jeff Garik-a.
 
*Dodatna zanimljivost je to što nitko od __Core developera__ nije pozvan na NYA dogovor.*

### UAHF i Bitcoin Cash

Nakon inicijalnog dogovora o kompromisu i implementaciji dolje navedenog rješenja.

Bitmain je prekršio dogovor i 1.8.2017 pokrenuli su [UAHF (User Activated Hard Fork)][UAHF]. 
Ovim forkom je nastao Bitcoin Cash, razlika u odnosu na Bitcoin Core je 8mb veličina blokova i "podrška" za ASICBoost.

Na slikama možemo vidjeti neke od ključnih zagovornika SegWit2x (Jihan Wu i Roger Ver) kako promoviraju Bitcoin Cash, time je jasno gdje oni stoje i da su zapravo protiv Bitcoina.

![01](../Images/01.png)

![02](../Images/02.png)

Od početnog broja od 56 kompanija u NYA dogovoru, 10 kompanija je odustalo od dogovora, dok je 8 kompanija prešlo na Bitcoin Cash. Ostaje nam 38 kompanija koja još podržava SegWit2x nadogradnju (u trenutku pisanja ovog teksta).

[Ovdje možete pratiti popis kompanija][segwitstatus] koje su za ili protiv.


## Segwit2x kao korporativni napad na Bitcoin

### Nedostatak konsenzusa. 

Naime, sve kompanije i Bitcoin rudari (uključujući kineske rudare koji su se unatoč potpisivanju dogovara odvojili od glavnog Bitcoin lanca na Bitcoin Cash) su potpisali NYA dogovor, no nitko nije pitao Core developere slažu li se s time, no ni Core developeri nisu toliko bitni kao što su bitni sami korisnici Bitcoina.

Ljepota Bitcoina kao decentraliziranog protokola je baš u tome što je demokratski, svatko može glasati tako da kod kuće ima Bitcoin čvor koji primjenjuje stroga pravila po kojima neki blok smatra validnim. Tako da ako rudari aktiviraju SegWit2x i rudare veće blokove, čvorovi ih neće prihvatiti jer po pravilima Bitcoina ti blokovi nisu validni.

Rudari će se automatski forkati na drugi lanac, dok će rudari koji rudare po pravilima ostati na originalnom Bitcoin lancu.

Situacija s naknadama za transakcije se pomalo poboljšava, SegWit transakcije se polako sve više i više koriste i naknade za transakcije padaju, ali i dalje postoji problem naknada koje su trenutno skuplje nego bi trebale biti.  No, ovakav hard fork ne treba olako shvaćati.

[Ovdje][SegWitTx] možemo vidjeti koliko se SegWit zapravo koristi.

### Zbunjujuće je

Glavni Bitcoin lanac se forkao već 2 puta, od 1.8. imamo Bitcoin Cash, a od 23.10. imamo i [Bitcoin Gold]. 
Ako dođe do novog forka u studenom i dobijemo Bitcoin2x, imat ćemo četiri Bitcoina.

To će prouzročiti kaos na burzama i među ljudima koji su novi u kriptovalutama.
Kao i gubitak sredstava zbog slučajnog slanja Bitcoina na Bitcoin2x adresu ili Bitcoin Cash na Bitcoin2x adresu.

Konsenzus zajednice je da se hard fork treba planirati godinu dana unaprijed, pa čak i dvije godine, ovisno o kompleksnosti. Pogotovo na sustavu čija vrijednost u vrijeme pisanja ovog članka iznosi ~100 milijardi USD.

Uzmimo za primjer [Ethereum], nedavno je prošao kroz uspješan hard fork i implementaciju Byzantium nadogradnje o kojoj možete pročitati [ovdje][ethroadmap]. Taj hard fork je planiran od samog početka, tako da nije ni čudo da je sve prošlo bez problema.

SegWit2x je zamišljen da se aktivira šest mjeseci nakon potpisivanja NYA dogovora.

### Replay protection

Vrlo bitna stavka kod svakog forka je zaštita ponavljanja transakcija na oba lanca.
Da pojasnimo, blockchain do trenutka forka dijeli istu povijest (adrese, transakcije, [privatne][privatekey] i [javne][publickey] ključeve). 

Nakon forka, privatni i javni ključevi su isti na oba forka, zato i dobijemo isti broj coina na drugom forku (Primjer: Bitcoin Cash, Ethereum Classic). No, kad pošaljemo transakciju na lancu A, ona je potpisana našim privatnim ključem i kompletna je. Pošto transakcija ima sve potrebne elemente, netko može uzeti transakciju na lancu A i odaslati je na lancu B, tako da bi u slučaju da želimo prodati Bitcoin2x coine, šaljući njih na neku adresu, netko bi mogao uzeti našu Bitcoin2x transakciju i odaslati ju na originalnom Bitcoin lancu i tako bi mogli ostati bez Bitcoina na originalnom lancu.

Zaštita protiv ponavljanja transakcija za SegWit2x trenutno ne postoji.

*[Ovdje][replayprotection] možete pročitati detaljniji opis zaštite ponavljanja.*


### Zadnje ali možda i najvažnije

Na Redditu je osvanuo [post][redditpost] koji povezuje [DCG] (Digital Currency Group), kompaniju koja forsira SegWit2x implementaciju, s bankarskim vezama kao što su MasterCard i slično.
[Ovo][dcgleaders] su ljudi koji vode DCG.

Tu su tri člana odbora i jedan savjetnik odbora, troje članova su poprilično zanimljivi:

**Glenn Hutchins**: Bivši savjetnik predsjednika Clintona, član odbora **Federal Reserve Banke New Yorka, gdje je trenutni član**.

**Barry Silbert**: CEO DCG-a (Digital Currency Group) i bivši investicijski bankar u Houlihan Lokey.

**[Lawrence H. Summers][LawrenceSummers]**: Vodeći ekonomist u "World Bank" od 1991-1993.
1993 . Summers postaje pod tajnik u Ministarstvu financija SAD-a pod Clintonovom administracijom.
1995 . je unaprijeđen je kao zamjenik tajnika riznice, podređen svom mentoru Robertu Rubin-u.
1999 . Nasljeđuje Rubin-a kao tajnik riznice.

Daljnje istraživanje nas dovodi do kompanije BitGo koja nadzire razvoj s Jeff Garzik-om.
[BitGo] ima uslugu koja je ništa više nego PayPal za Bitcoin, treća strana koja osigurava da se dupla potrošnja ne dogodi, ako osobe ne žele čekati za potvrdu transakcije.

Bitcoin je dizajniran tako da isključi treće strane i omogući transakcije striktno s osobe na osobu. Nova transakcija se obično uključi odmah u prvi blok, a jedna potvrda bi trebala biti dovoljna za većinu ljudi, pogotovo ako su mali iznosi.

[Ovdje][mastercard] možemo vidjeti kako MasterCard izjavljuje da su protiv Bitcoina i kriptovaluta općenito.

Možemo li vjerovati DCG-u da je SegWit2x pravi put za Bitcoin? 

Možemo li vjerovati bankarima koji su uzrok financijskih kriza?

Tim istim bankarima kojima su kriptovalute trn u oku, jer kriptovalute vraćaju moć narodu.

Ako SegWit2x miče Core developere iz ove priče, koga stavlja na njihovo mjesto? MasterCard i bankare? 

No, kao i sve, ni ovo nije crno bijelo, [ovdje][blockstream] raspravljamo potencijalni napad s druge strane.

Što Vi mislite? Napišite nam u komentare.

## Što očekivati oko cijene Bitcoina tijekom forka

*Napomena: Ovo nije nikakav investicijski savjet, već osobno mišljenje i treba ga se tumačiti kao takvo.*

Pretpostavljamo da će se cijena kretati isto kao i uoči prošlih forkova.
Nedugo prije forka će cijena Bitcoina porasti zbog [FOMO], a [altcoini][altcoins] će najvjerojatnije pasti.
Nakon samog forka, dio SegWit2x coina će se prodati za Bitcoin, a dobar dio novca će se vratiti u altcoine. Bitcoin bi mogao porasti u vrijednosti kao i nakon Bitcoin Cash forka.

Neke od mogućnosti su: 
1. Prodaja Bitcoina uoči forka dok se sve ne smiri
2. Pokušaj tempiranja tržišta i swing trading (Ne preporučuje se)
3. [HODL], sigurno rješenje ako čvrsto vjerujete u projekt.

Ako iz nekog razloga niste sigurni da možete čuvati privatne ključeve na sigurnom, slobodno se javite [nama][manageportfolio].




[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[SegWit]: https://segwit.org
[privatekey]: https://bitfalls.com/hr/glossary/#private-key
[ASICBoost]: https://www.asicboost.com
[ABOOSTGregMax]: https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-April/013996.html
[hash]: https://bitfalls.com/hr/glossary/#hash
[Raiden]: https://bitfalls.com/hr/2017/10/02/ethereums-development-roadmap-metropolis/#raiden-network
[LightningNetwork]: https://www.youtube.com/watch?v=MpfvhiqFw7A
[UAHF]: https://cointelegraph.com/explained/uasf-vs-uahf-explained
[NYA]: https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77
[segwitstatus]: http://segwit.party/nya/
[fork]: https://bitfalls.com/hr/glossary/#fork
[Ethereum]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[ethroadmap]: https://bitfalls.com/hr/2017/10/02/ethereums-development-roadmap-metropolis/
[publickey]: https://bitfalls.com/hr/glossary/#public-key
[Bitcoin Gold]: https://btcgpu.org
[redditpost]: https://www.reddit.com/r/btc/comments/743qb8/is_segwit2x_the_real_banker_takeover/
[dcg]: http://dcg.co
[dcgleaders]: http://dcg.co/who-we-are/
[LawrenceSummers]: https://en.wikipedia.org/wiki/Lawrence_Summers
[BitGo]: https://www.bitgo.com/solutions
[mastercard]: https://www.youtube.com/watch?v=Tu2mofrhw58](https://youtu.be/Tu2mofrhw58?t=170
[blockstream]: https://bitfalls.com/hr/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/#segwit2x
[replayprotection]: https://bitfalls.com/hr/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/#replay-attack
[SegWitTx]: http://segwit.party/charts/#
[FOMO]: https://bitfalls.com/hr/glossary/#fomo
[altcoins]: https://bitfalls.com/hr/glossary/#alt-coins
[HODL]: https://bitfalls.com/hr/glossary/#hodl
[manageportfolio]: https://bitfalls.com/hr/portfolio-management/