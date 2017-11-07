Segwit? Segwit2x? Fork? NYA agreement? Pojmovi koje ste možda čuli u proteklih nekoliko mjeseci, a ne znate što znače? U ovom članku ćemo vam pojasniti spomenute pojmove i što se krije iza njih.

*Ako ste novak u kriptovalutama, da biste razumjeli terminologiju iz teksta dolje preporučujemo da pročitate [uvod u blockchain][blockchain].*


## Problematika

Svaki blockchain ima istu slabost, a to je skalabilnost. Kad blockchain dođe do točke zasićenja gdje ima više transakcija nego mreža može procesirati, brzina kojom se transakcije izvršavaju se smanjuje. Time se naknada za transakcije povećava jer rudari u blockchain prvo uključuju transakcije s većom naknadom, a tek onda idu ostale.

Drugi problem je način optimizacije rudara po imenu [ASICBoost]. ASICBoost omogućava veću efektivnost rudarenja smanjivši potrošnju električne energije u omjeru na broj [hasheva u sekundi][hashrate]. Kineski proizvođač opreme za rudarenje Bitmain imao je ugrađen ASICBoost u svoje rudarske uređaje i time [zarađuje ~30% Bitcoina više][ABOOSTGregMax] od ostalih.

U nalaženju rješenja za problem ASICBoosta i skalabilnosti imamo dvije suprotstavljene strane: 

1. Core developeri (programeri koji rade na Bitcoin protokolu)
2. Kineski rudari

### Prvo rješenje (Core developeri): 

**Core developeri** preferiraju [Segregated Witness][SegWit] (SegWit u daljnjem tekstu) koji je kompleksnije rješenje, ali isplativije na duže staze. Također postavlja temelje za *Lightning network* (LN) koja će dodatno povećati skalabilnost s off-chain transakcijama. 

Tehnologija Lightning Networka je slična i ima istu namjenu kao [Raiden mreža][Raiden] na [Ethereumu][eth].

Ukratko, Lightning mreža pomoću pametnih ugovora i platnih kanala omogućuje masovni skok u transakcijama koje su prvotno off chain (nisu na blockchainu). Time su omogućene i mikrotransakcije jer su transakcijske naknade nepostojeće - na kraju se sve pošalje na blockchain u jednoj velikoj transakciji za koju se plati naknada. Nedostatak je potencijalno formiranje bitbanaka i centraliziranih servisa kroz koje se te transakcije vrše prije nego budu poslane na glavni blockchain, što znači novo formiranje bankovnog sektora u svijetu kriptovaluta. Također, LN oduzima transakcijske naknade od rudara u velikom dijelu i daje ih tim centraliziranim entitetima što, kada uzmemo u obzir ["konačnost"][finite] Bitcoina, ne zvuči dobro.

Za napredne korisnike koje zanima više, [ovaj video će biti koristan][LightningNetwork] (na engleskom).

#### Što je SegWit

SegWit je tehnologija koja omogućava blockchainu povećavanje broja transakcija.
No, kako SegWit funkcionira?  

Bitcoin transakcija se sastoji od informacija kao što su veličina transakcije, koliko ulaza i izlaza transakcija sadrži, kolika je naknada za rudare, kada je transakcija uključena u blok itd.

Ovdje je najbitniji dio da **svaka** transakcija mora biti **potpisana [privatnim ključem][privatekey]**. Upravo taj potpis zauzima većinu mjesta u transakciji, no bez tog potpisa ne znamo je li transakcija valjana.

Core developeri su SegWitom (Segregated Witness = _odvojeni svjedok_) odlučili "prepoloviti transakciju" i odvojiti potpis od ostatka transakcije. Time smanjivši veličinu transakcije, efektivno su povećali kapacitet bloka.

Čvorovi koji žele provjeriti legitimitet transakcija mogu zatražiti i potpise za svaku transakciju tako da imaju instaliran čvor koji podržava SegWit npr. Bitcoin Core. To ujedno znači da cijeli sustav funkcionira na povjerenju do kad se legitimnost transakcija manualno ne provjeri dodatnih zahtjevom za potpisima.

### Drugo rješenje (Rudari):

Kineski rudari, s vlasnikom Bitmaina Jihanom Wu na čelu, zagovarali su povećanje blokova s 1mb na čak 8mb. To nije dugoročno rješenje, jer kako se Bitcoin bude sve više i više koristio, tako ćemo nakon nekog vremena opet imati isti problem kapaciteta.

Dodatni veliki razlog zašto su se kineski rudari bunili je taj što SegWit **onemogućava ASICBoost**, a time ostaju bez velike prednosti.

Nadalje, ako se veličina blokova poveća na 8mb, tako drastično povećanje kapaciteta blokova bi negativno utjecalo na čvorove u mreži jer sada moraju pohraniti i obraditi osam puta više podataka u istom vremenskom razdoblju. Inicijalna sinkronizacija čvora će također trajati puno duže (proces preuzimanja i validiranja cijelog blockchaina nakon instalacije Bitcoin softvera).  Trebat će više resursa da se čvor održi, u smislu diskovnog prostora i internetske propusnosti.

S vremenom postoji mogućnost da si zbog veličine blockchaina obični ljudi neće moći priuštiti svoj čvor, nego će si to moći priuštiti samo veliki podatkovni centri i tvrtke, što će dovesti do centralizacije i pretvoriti Bitcoin u korporativnog talca, slično situaciji s bitbankama iz Lightning Network situacije opisane gore. Onaj tko kontrolira čvorove, kontrolira i Bitcoin, zato je bitno da mogućnost pogonjenja vlastitog Bitcoin čvora ostane pristupačna svima.

Kao što smo opisali u članku o [konačnosti Bitcoina][finite], ako dođe do centralizacije čvorova, oni koji ih kontroliraju mogu podići limit s 21 milijun Bitcoina na koliko žele, mogu odbijati inače valjane transakcije, mogu mijenjati pravila protokola. To je vrlo opasno za Bitcoin, a i za ostatak kritpo prostora. 

*Zbog toga što je Bitcoin protokol zasnovan na principu nepovjerenja, potiče se da sami provjerimo istinitost transakcija na mreži tako da imamo vlastiti čvor.*


### Treće rješenje (kompromis):

Prvo aktivirati SegWit, a kasnije povećati blokove.

Rješenje se čini kao dobar kompromis, zar ne? 

Unatoč gore navedenim razlozima zašto nijedna metoda nije optimalna, više je zabrinjavajuće tko gura SegWit2x i tko stoji iza toga.

#### NYA dogovor i SegWit2x

[New York Agreement][NYA] je dogovor između nekih od najvećih kompanija u Bitcoin prostoru i velikih rudara. Dogovoreno je da će se prvo aktivirati SegWit, a 90 dana kasnije SegWit2x koji će još podići veličinu bloka na 2mb, što bi u kombinaciji s SegWitom uzrokovalo teoretsko povećanje kapaciteta na cca 8mb. 

Cijeli razvoj Segwit2x je nadgledan od strane Jeff Garzik-a, jednog od originalnih autora Bitcoin blockchain softvera. Tom dogovoru - koliko iz principa (dogovori iza zatvorenih vrata nisu u duhu Bitcoina) toliko iz činjenice da ih većina nije bila pozvana - nisu prisustvovali Bitcoin Core developeri.

Od početnog broja od 56 kompanija u NYA dogovoru, 10 kompanija je odustalo od dogovora, dok je 8 kompanija prešlo na Bitcoin Cash. Ostaje nam 38 kompanija koje još podržavaju SegWit2x nadogradnju (u trenutku pisanja ovog teksta).

[Ovdje možete pratiti popis kompanija][segwitstatus] koje su za ili protiv.

#### UAHF i Bitcoin Cash

Nakon inicijalnog dogovora o kompromisu i implementaciji navedenog rješenja, prije spomenuti proizvođač rudarske opreme Bitmain je prekršio dogovor i 1.8.2017. pokrenuli su [UAHF (User Activated Hard Fork)][UAHF] kojim je nastao Bitcoin Cash. Bitcoin Cash ima blokove od 8mb i zaštitu od _replay napada_ (napada duplog trošenja valuta koji smo opisali u [Bitcoin Gold] članku).

Na slikama dolje možemo vidjeti neke od ključnih zagovornika SegWit2x (Jihan Wu i Roger Ver) kako promoviraju Bitcoin Cash. Zašto bi još uvijek brinuli oko SegWit2x ako su dobili svoju željenu valutu u obliku Bitcoin Cash-a mnogima [nije jasno][whycare].

![01](../Images/01.png)

![02](../Images/02.png)


## Daljnji razvoj

Naposljetku, ni Core developeri ni rudari nisu toliko bitni kao što su bitni sami korisnici Bitcoina. Ljepota Bitcoina kao decentraliziranog protokola je baš u tome što je demokratski, svatko može glasati tako da kod kuće ima Bitcoin čvor koji primjenjuje stroga pravila po kojima neki blok smatra validnim. Ako rudari aktiviraju SegWit2x i rudare veće blokove, čvorovi ih neće prihvatiti jer po pravilima Bitcoina ti blokovi nisu validni. Rudari će se automatski forkati na drugi lanac, dok će rudari koji rudare po pravilima ostati na originalnom Bitcoin lancu. 

S druge strane, ako čvorovi izmjene svoj softver na takav da prima transakcije s većim blokovima, tada taj lanac postaje glavni, i onaj s manjim blokovima odumire. Sve je u rukama korisnika, no nažalost lobiji dezinformacija i osobnih koristi su već sada u kripto svijetu vrlo jaki, te je do objektivnih informacija vrlo teško doći.

Kod trenutnog Bitcoina, situacija s visokim naknadama za transakcije se pomalo poboljšava, SegWit transakcije se polako [sve više i više koriste][SegwitTx] i naknade za transakcije padaju, ali i dalje postoji problem naknada koje su trenutno skuplje nego bi trebale biti. Unatoč problemima, ovakav hard fork ne treba olako shvaćati.

Glavni Bitcoin lanac se nedavno forkao dva puta: od 1.8. imamo Bitcoin Cash, a od 23.10. imamo i [Bitcoin Gold]. Ako dođe do novog forka u studenom i dobijemo Bitcoin2x, imat ćemo četiri "glavna" Bitcoina, ne brojeći sve forkove koji su nastali prije (Litecoin, Dash, ZCash, Bitcoin Unlimited, itd.)

To će prouzročiti dodatni kaos na burzama i među ljudima koji su novi u kriptovalutama, kao i gubitak sredstava zbog slučajnog slanja Bitcoina na Bitcoin2x adresu ili neke druge nekompatibilne kombinacije.

Konsenzus zajednice je da se hard fork treba planirati godinu dana unaprijed, pa čak i dvije godine, ovisno o kompleksnosti, pogotovo na sustavu čija vrijednost u vrijeme pisanja ovog članka iznosi ~150 milijardi USD.

Uzmimo za primjer [Ethereum] - nedavno je prošao kroz uspješan hard fork i implementaciju Byzantium nadogradnje o kojoj možete pročitati [ovdje][ethroadmap]. Taj hard fork je planiran od samog početka 2014., tako da nije ni čudo da je sve prošlo bez problema. Unatoč diskusijama koje su trajale godinama prije samog dogovora, SegWit2x je zamišljen da se aktivira svega tri mjeseca nakon potpisivanja NYA.

## Napad centralnih banaka

Na Redditu je osvanuo [post][redditpost] koji povezuje [DCG] (Digital Currency Group), kompaniju koja predvodi, financira, i planira SegWit2x implementaciju, s bankarskim vezama kao što su MasterCard i slično (poznati neprijatelji kriptovaluta).

[Ovo][dcgleaders] su ljudi koji vode DCG. Troje članova su posebno zanimljivi:

**Glenn Hutchins**: Bivši savjetnik predsjednika Clintona, član odbora **Federal Reserve Banke New Yorka, gdje je trenutni član**.

**Barry Silbert**: direktor DCG-a (Digital Currency Group) i bivši investicijski bankar u Houlihan Lokey.

**[Lawrence H. Summers][LawrenceSummers]**: Vodeći ekonomist u "World Bank" od 1991-1993.
1993 . Summers postaje pod tajnik u Ministarstvu financija SAD-a pod Clintonovom administracijom.
1995 . je unaprijeđen je kao zamjenik tajnika riznice, podređen svom mentoru Robertu Rubin-u.
1999 . Nasljeđuje Rubina kao tajnik riznice.

Daljnje istraživanje nas dovodi do kompanije BitGo koja nadzire razvoj s Jeff Garzik-om.
[BitGo] ima uslugu koja je ništa više nego PayPal za Bitcoin, treća strana koja osigurava da se dupla potrošnja ne dogodi, ako osobe ne žele čekati za potvrdu transakcije (_bitbanka_).

Bitcoin je dizajniran tako da isključi treće strane i omogući transakcije striktno s osobe na osobu. Nova transakcija se obično uključi odmah u prvi blok, a jedna potvrda bi trebala biti dovoljna za većinu ljudi, pogotovo ako su mali iznosi.

[Ovdje][mastercard] možemo vidjeti kako MasterCard izjavljuje da su protiv Bitcoina i kriptovaluta općenito.

Možemo li vjerovati DCG-u da je SegWit2x pravi put za Bitcoin? Možemo li vjerovati bankarima koji su uzrok financijskih kriza? Tim istim bankarima kojima su kriptovalute trn u oku, jer kriptovalute vraćaju moć narodu.

Ako SegWit2x miče Core developere iz ove priče, koga stavlja na njihovo mjesto? MasterCard i bankare? 

No, kao i sve, ni ovo nije crno bijelo, [ovdje][blockstream] raspravljamo potencijalni napad s druge strane.

## Što očekivati oko cijene Bitcoina tijekom forka

*Napomena: Ovo nije nikakav investicijski savjet, već osobno mišljenje autora i treba ga se tumačiti kao takvo.*

Pretpostavljamo da će se cijena kretati isto kao i uoči prošlih forkova.

Nedugo prije forka će cijena Bitcoina porasti zbog [FOMO], a [altcoini][altcoins] će najvjerojatnije pasti (ovo je zadnjih par tjedana već u tijeku).

Nakon samog forka, coin jednog forka će se prodati za coin drugog forka, ili za altcoine. Bitcoin koji prevlada bi mogao porasti u vrijednosti kao i nakon Bitcoin Cash forka.

Ono što možete učiniti da se okoristite prilikom:

1. Prodaja Bitcoina uoči forka dok se sve ne smiri
2. Pokušaj tempiranja tržišta i swing trading (ne preporučuje se - visok rizik, ali potencijalna visoka isplata)
3. [HODL], sigurno rješenje ako čvrsto vjerujete u projekt ili ako jednostavno želite zadržati oba coina

Bitno je napomenuti da ukoliko držite svoj Bitcoin na nekoj burzi ili mjenjačnici, na njima je da vam daju coin drugog lanca kada se desi fork - oni to mogu ali ne moraju. Zato je najsigurnije (ne samo za vrijeme forka nego i općenito) imati svoje kriptovalute uvijek kod sebe: uvijek imajte [potpunu kontrolu][paper] nad svojim privatnim ključem.

Ako iz nekog razloga niste sigurni da možete čuvati privatne ključeve na sigurnom, slobodno [nam se javite][manageportfolio].


[paper]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[hashrate]: https://bitfalls.com/hr/glossary/#hash-rate
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
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[whycare]: https://www.reddit.com/r/btc/comments/75u35x/bitcoin_cash_vs_b2x/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
