Na vikend 23. i 24. rujna 2017 održao se [Novathon], hackathon PBZ-a. Cilj je (barem na papiru) bio napraviti nova korisnicima pristupačna rješenja u sektoru financijskih tehnologija (fintech).

Naš tim Bitfalls pristupio je izazovu s, naravno, naglaskom na kriptovalute.

## Ideja: državna kriptovaluta

Budući da se banke "boje" [kriptovaluta][cc] zbog decentralizacije i pretjerane slobode od centralnog financijskog sustava, postoji velika šansa da će najkorumpiranije i najpohlepnije vlade gurnuti kriptovalute [u ilegalu][unstoppable].

Taj "rat protiv kriptovaluta" imao bi isto toliko efektivnosti kao i rat protiv droge. Svi koji kriptovalute već koriste nastavili bi ih koristiti _u podzemlju_, cijeli ekosustav kriptovaluta bio bi još bogatiji prijevarama zbog nedostatka regulacije i odsutnosti jakih državnih igrača, pojavili bi se [kripto karteli kojima je profit jedini cilj][gold], a najviše bi stradali prosječni, "rekreativni" korisnici, dok bi država ostala bez velikog dijela kolača - potencijal za zaradu i za porezna ubiranja je nemjerljiv.

Zašto, stoga, ne spojiti ta dva svijeta? Zašto ne povezati korporativno bankarski i državni svijet s novim, revolucionarnim svijetom kripto tehnologija i [blockchaina][bc], te time omogućiti civilima lagan, legalan, i reguliran ulaz u kripto svijet, a ujedno i drastično tehnološki unaprijediti postojeći sustav?

## dKuna

![Dkuna logo](https://bitfalls.com/wp-content/uploads/2017/10/01-6.png)

Naša ideja zasnivala se na kriptovaluti koju smo nazvali "dKuna" ili "digitalna kuna". Ime je nebitno i može biti bilo što - kunacoin, HRKoin, ili što već. Koncept je primjenjiv na bilo koju državnu valutu - zbog lokaliteta u kojem smo izrađivali projekt smo odabrali kunu, no mogao je to isto tako biti Euro, Yen, ili nešto treće.

Radi se o [ERC20 tokenu][eth], dakle kriptovaluti građenoj _pametnim ugovorom_ (programom) na [Ethereum][eth] platformi. Budući da se radi o kriptovaluti na javnom blockchainu, sve transakcije su [anonimne][anon] ali vidljive i lako čitljive iz raznih [alata koji služe za pregled blockchaina][blockex].

Ideja je bila sljedeća:

- ugovor (misli se na _pametni ugovor_ - program na blockchainu) koji kontrolira valutu ima mogućnost kreiranja novih dKuna tokena, i uništavanja postojećih koji mu se pošalju

- HNB, koji bi bio vlasnik tog ugovora, imao bi mogućnost kreiranja novih tokena kada primi depozit, i uništavanja tokena kada isplati depozit. Npr. ako tvrtka X depozitira 30000kn u HNB za svrhu dKune, tvrtka X dobiva 30000dkn, a 30000 fiat kuna se zaključava u HNB. Kada tvrtka X pošalje npr. 15000dkn nazad u HNB, depozit u veličini od 15000 se vraća, i 15000dkn se uništava i miče iz cirkulacije. To onemogućava divlju inflaciju jer se omjer digitalnih i običnih kuna održava i jer je kreacija novih dKuna transparentna i vidljiva na blockchainu

- ugovorom koji izvršava funkcije kreiranja novih tokena i uništenja postojećih može upravljati više osoba, ali je za upravljanje istim potrebno više ključeva. Tako primjerice u HNBu 10 bitnih ljudi može imati ključeve, a za pokretanje funkcije "napravi nove tokene" u ugovoru može biti potrebno pet od tih deset. Usporedite to s trezorom koji se otključava istovremenim okretom ključa od više osoba. Nadalje, nadležne službe imaju istu mogućnost - tako npr. EU inspekcija može imati deset svojih ključeva, no njima se može podesiti da trebaju sedam od tih deset da bi pokrenuli neke komande. Interpol može dobiti svoje ključeve i isto tako po potrebi preuzeti kontrolu. Čim više nadležnih službi ima ograničen ali validan pristup logici dKuna, tim je manja šansa za korupciju.

- ugovor ima funkciju prijenosa vlasništva. U slučaju da u HNBu pet od onih deset ljudi izgubi svoje ključeve ili sumnja na to da su procurili, lako je uzeti preostalih pet ključeva i prenijeti vlasništvo ugovora na novu adresu koja treba drugih pet od drugih deset ključeva, time nepovratno resetiravši cijeli sigurnosni sustav dKuna ugovora u roku od nekoliko minuta. Procurjeli ključevi postaju beskorisni. Ova funkcija je korisna i u slučaju da država koja koristi neku dValutu počne legalno odmicati (vidi Venezelu ili Zimbabwe), te tada nadležno tijelo (npr. EU, UN, ili neko drugo međunarodno udruženje) može preuzeti kontrolu nad dKuna sustavom i zaustaviti kaos.

_Bitno je napomenuti da naša Novathon implementacija nije stala samo na ideji. Kriptovaluta i sustav oko nje razvijeni su u potpunosti, i bila je u funkciji za vrijeme Novathona - slali smo dKune jedni drugima._

### Moguće upotrebe

**Primarni ciljevi dKuna su dakle:**

- sigurnost i globalna kompatibilnost
- potpuno odstranjenje korupcije iz državnih krugova i transparentnost prema građanima
- potpuna automatizacija financijske birokracije
- bezbolni ulaz građana u kripto svijet, i ulaz lokalne valute na globalno tržište

Pogledajmo svaki u malo više detalja.

#### Sigurnost i globalna kompatibilnost

![Ilustracija lopova kako krade nešto s laptopa](https://bitfalls.com/wp-content/uploads/2017/10/02-4.jpg)

Budući da je dKuna ERC20 token, to znači da je se može slati na bilo koju Ethereum adresu. Možete svoje kune spremiti na [hardverski digitalni novčanik][ledger], na mobitel, na računalo, ili na [komad papira][paper]. Možete ih u momentu poslati s jedne adrese na drugu, s jednog kraja svijeta na drugi, bez da primatelj mora imati račun u kompatibilnoj banci, bez trodnevnog čekanja za SWIFT transfere, bez provizija. Ne samo to - već ih je trivijalno slati i iz banke u banku bez odlaska u poslovnicu. Korištenje običnog [Ledger][ledger] uređaja ili novčanika poput [MyEtherWallet][mew] omogućava slanje dKune u bilo koju banku koja je prešla na sustav dKune - a kod nas bi to bila svaka banka ukoliko bi HNB prihvatio dKune.

Bankama je trivijalno dodati funkcionalnost slanja i primanja dKune, pa ta mogućnost postaje dostupna i u netbanking aplikacijama u vrlo kratkom roku. Prisjetimo se - radi se o javnom blockchainu koji je potpuno globalno osiguran, o infrastrukturi koja već postoji i gotovo je neuništiva. S strane banaka, ulaganja u implementaciju ovog sustava su trivijalna.

Vrijedi spomenuti i da, iako se čini čudno dati desetorici ljudi kontrolu nad financijskom infrastrukturom države, trenutni sustav ima još ozbiljniju centralnu točku pada sustava. Jedan administrator ili programer bankovnog sustava koji nije dovoljno spavao noć prije može sam baciti cijeli sustav u kaos običnim klikom miša. Kod Ethereuma i pametnih ugovora to nije moguće, jer je program osiguran blockchainom, a kopiju blockchaina imaju i verificiraju svi. Do grešaka u kodu može doći jedino i samo pri originalnom pisanju pametnog ugovora koji, kad se ispegla, postaje teoretski nepogrešiv.

#### Potpuno odstranjenje korupcije

Zbog javne ali [anonimne][anon] prirode blockchaina, sve transakcije su vidljive - od onih transakcija koje pokreću funkcije za kreiranje novih dKuna tokena, do onih koje se dešavaju kao dio poslovanja. Uzeti vreću keša i jednostavno odletjeti na Bahame postaje fizički nemoguće, jer dKune neće biti moguće potrošiti u tom iznosu bez da se transakcija vidi u zapisima.

Javna priroda blockchaina također osigurava automatiziranu reviziju HNBovih zaliha fiat valute koja je uzrokovala kreaciju novih tokena. Tako, ako EU primijeti da se kreiralo 100000 novih dKn, u HNBovom trezoru mora biti dodatnih 100000 HRK u novčanicama. Ako nije tako (a revizija to tada lako provjerava jer zna **točno** koliko dKuna postoji u cirkulaciji), netko igra protiv sustava. S obzirom da se sve transakcije potpisuju ključevima, i svaki poziv funkcije ugovora je javan, znati će se tko pliva uzvodno.

Neprimjećeni krediti od nekoliko miljardi postaju nemogući, i društvo ne može trošiti više nego ima. Nekontrolirana inflacija postaje nemoguća (trenutno ne znamo sa sigurnošću koliko HRK se pušta u cirkulaciju i kada).

#### Potpuna automatizacija financijske birokracije

![Robot crta robota koji crta robota koji crta robota, i tako u nedogled](https://bitfalls.com/wp-content/uploads/2017/10/03-5.jpg)

dKunom fiskalni sustav postaje nepotreban. Budući da su sve transakcije bilježene na blockchainu, ako se tvrtka X koja je uzela 30000dkn identificira u poreznom sustavu kao vlasnik Ethereum adrese XYZ, porezna ima mogućnost automatski ne samo napraviti reviziju svih transakcija učinjenih za vrijeme poslovanja te tvrtke, nego i automatski procijeniti prihode i rashode i zaključiti te naplatiti porezno dugovanje, bez ikakvih potreba za intervencijom od knjigovodstvenih servisa.

Biljezi nestaju iz cijelog sustava jer transakcije postaju trajne i dokazive transakcijskim kodom koji je nepromjenjiv. Čekanja u redovima drastično padaju jer jer softver za korištenje Ethereum blockchaina javno dostupan - bilo Ledger uređajem, MyEtherWallet stranicom, ili mobilnom aplikacijom, dKune se lako šalju bilo kome bilo kada u bilo koje doba dana, budu istog momenta vidljive i nepromjenjivo dokazive. Potreba za računima nestaje.

Da, to znači da će mnogo ljudi dobiti otkaz. Financijski inspektori, revidori, razne vrste posrednika, čak i knjigovođe u nekim slučajevima. Sve će biti automatizirano. Zašto trošiti ljudsku snagu na nešto toliko suvišno, kad te financijske eksperte možemo obrazovati i ponovno zaposliti u [čitanju blockchaina][blockex] i promatranju situacije iz daljine te sprječavanju korupcije?
 
#### Kripto tržište = globalno tržište

Zbog ERC20 standarda i mogućnosti slanja kuna na međunarodne Ethereum adrese i burze, otvara se novi svijet korištenja kuna običnim građanima. Od [ulaganja u druge kriptovalute][folio], do lakog i transparentnog pristupa [web shopovima][shop], globalizacijom kune kroz sustav kriptovaluta namjerno se uzrokuje pucanje mjehura u kojem je Hrvatska pre dugo zarobljena. Kuna postaje globalna valuta.

No, što je u svemu tome prednost za banke? Zašto bi oni oslobodili građane na taj način i odrekli se marže?

Ako i stavimo na stranu da će se ovo prije ili kasnije svejedno desiti, i da će građani ionako  pobjeći od tradicionalnog bankarskog sustava, korist kod implementacije za same banke bila bi sljedeća:

- investicijski fondovi bazirani na kriptovalutama već sada su aktivni, no vode ih privatne firme. Pogledajte hrvatski [Digital Assets Power Play](https://www.dapowerplay.com/), ili projekte poput [ICONOMI](http://iconomi.net), [Melonport](https://melonport.com/), [Prism](https://info.shapeshift.io/blog/tags/prism), i druge. Provizije koje banke ovdje mogu ubrati su u količinama koje nadmašuju hrvatski godišnji GDP, samo zbog globalne pristupačnosti te tehnologije.
- štednje na kriptovalutama postaju mogućnost - bilo štednje u dKuni, ili štednje u nekoj drugoj kriptovaluti otpornoj na inflaciju a kupljenoj dKunom.
- provizije za mijenjanje kriptovaluta su još jedna mogućnost zarade
- posuđivanja i krediti u kriptovalutama postaju sigurniji i moralno cjelovitiji - uvjeti se lako zapisuju u _pametni ugovor_ i automatski ispunjuju kada zaduženik otplati ratu kredita. Kamata, otplata, i svi ostali uvjeti lako se isprogramiraju u same ugovore i budu automatski izvršeni ovisno o nekim okidačima. To je drukčije od tipičnog bankovnog sustava po tome što je ovaj globalan, transparentan, automatski, i vidljiv svima. Ovakav sustav je pošten.

![Iconomi](https://bitfalls.com/wp-content/uploads/2017/10/04-5.png)
_Graf ICONOMI investicijskog fonda_

Banke također mogu izdati debitne kartice s kojih se kriptovalute troše direktno - a budući da je dKuna ERC20 token, to znači da adresa koja drži dKune može držati i bilo koju drugu kriptovalutu baziranu na ERC20 standardu. To znači da netko tko spremi, primjerice, [OMG](http://omg.omise.co) kriptovalutu na adresu povezanu s svojom bankom, može koristiti debitnu karticu te banke da tu valutu troši u stvarnom životu. Kriptovalute time ulaze u mainstream, a banke ubiru proviziju na konverziji kao i sada s trošenjem deviznih debitnih kartica u dućanima s kunskim prometom. I ovakvi pokušaji već postoje, i uvelike su privatizirani - pogledajte [TenX][tenx], [Bitwalla], [Monaco][monaco], i slične. Primjetite da je svaka od njih VISA. VISA zna što radi i u koje novo tržište se ubaciti.

Gledati kriptovalute isključivo s kritične strane i zanemarivati potencijal za ne samo nadogradnju sustava nego i profit je naprosto suludo.

## Slična rješenja

Možda se čuli za USDT, ili USD Tether: kriptovalutu sličnog koncepta u kojoj je 1 USDT = 1 USD. Ukratko, USDT proizvodi jedna privatna tvrtka (Tether.io) koja nema revizije niti bankovne licence. Štoviše, iz sustava su ih izbacile sve veće banke i ne posluju s njima. Tetheri se još uvijek stvaraju i koriste na mjenjačnici Bitfinex za kupovinu Bitcoina. Očito je da se radi o velikoj kriminalnoj organizaciji koja laže svojim korisnicima i koristi svoju nepostojeću kriptovalutu da umjetno napumpa vrijednost Bitcoina. 

![Pumpanje cijene bitcoina](https://bitfalls.com/wp-content/uploads/2017/10/06-1.jpeg)

Za više o tome, pročitajte [ovaj članak][tether] ili dođite na [F2].

dKuna se razlikuje po tome što je javno čitljiva svim građanima, ali centralno regulirana i njome upravlja glavna državna financijska jedinica. Kontrolni pregled situacije ima organizacija koja je nadzorna njima, i tako dalje koliko god razina u visinu je potrebno. Da bi ovaj krug postao kriminalan poput Tethera, potrebna je apsolutna korupcija na svjetskoj razini, ne samo vlade i njoj nadležne vlade iz EU, već i svjetskih istraživačkih agencija, medija, internacionalne policije, itd. Ne samo to, nego će i svaki korak korupcije, ukoliko se počne razvijati, biti javno vidljiv zbog javne prirode blockchaina.

Osim spomenutog USD Tethera, od Novathona je više država predložilo relativno slična rješenja.

- Rusija [planira izdati][cryptoruble] kriptorubalj. Biti će moguća 1:1 zamjena kao u slučaju dKune, a ako vlasnik kriptorublja ne može objasniti njegovo porijeklo, mora platiti 13% poreza. To ujedno koči efikasno pranje novca, ali ne stavlja stop na kriptovalute općenito. U njihovom slučaju, nije izgledno da će država kontrolirati taj 1:1 omjer, pa su tako dodali stavku da će se na razliku zarade u vrijednosti kriptorublja također platiti 13% (npr. 1.1.2018. za 1 rubalj dobijemo 1 kriptorubalj. 1.1.2019. taj kriptorubalj sada vrijedi 10 rubalja. Prilikom isplate u rublje, na razliku se plaća 13% - kao porez na kapitalnu dobit). Nemaju depozitnu anti-inflacijsku mjeru u planu, no možda je naknadno dodaju.
- Dubai izbacuje [emCash][emcash]. Valuta nije vezana za nacionalnu u fiksnom omjeru, ali je državno sankcionirana i podržana za svakodnevnu trgovinu.

Bez obzira na te države koje mašu perjem blockchaina, osobno vjerujem da će nas Švedska prva iznenaditi vlastitom kriptovalutom napravljenom prema dKuna principu. Zapravo, gotovo sam siguran da će je koristiti *točno* kako je opisano. 

Oni su već sada društvo bez keša - nebrojeni dućani imaju natpis "Plastic is fantastic" i "No Cash", i čak i hot dog na ulici plaća se karticom. Keš im je toliko izbačen iz sustava da ima restorana i dućana koji ga uopće ne primaju. S obzirom na njihov fokus na transparentnost (npr. svaka potrošnja državnog službenika javno je vidljiva i dostupna svim novinarima), vjerujem da će prvi preći na ovaj sustav automatske revizije i potpune transparentnosti.

Mnogi se pitaju "zašto bi, ako im trenutni digitalni sustav tako dobro funkcionira?". Odgovor je: zato jer kad se radi o valuti na globalnom blockchainu, izaći iz sustava je lako kad dođe do državne korupcije na takvoj razini da se počnu plijeniti bankovni računi (što je vrlo lako u centraliziranom sustavu) ili počnu štampati [novčanice od parsto triljuna dolara][zim]. 

![Zimbabwe novčanica od 100 triljuna dolara](https://bitfalls.com/wp-content/uploads/2017/10/05.jpg)

Iz istog se razloga Amerikanci odbijaju odreći svojih oružja (barem na papiru). U ustavu im piše da imaju pravo na posjedovanje oružja u svrhu (između ostalog) mobilizacije za vrijeme obrane od tiranske vlade.

Šveđani cijene slobodu, i sloboda od korupcije im je apsolutno primarna.

### Privatni blockchain

Pitali su nas u više navrata zašto država ili neka banka ne bi napravila sve to, ali na privatnoj kopiji Ethereum blockchaina kao što to rade mnoge strane banke već sada. Tako transakcije postaju privatne, i sve je pod kontrolom tog entiteta bez da se ovisi o korisnicima u cijelom svijetu.

Ako stavimo na stranu nekompatibilnost s drugim bankama i glavnim Ethereum blockchainom, taj pristup ima točno nula prednosti, i dva velika nedostatka.

1. Privatni blockchain opet oduzima transparentnost i ne potiče povjerenje javnosti ništa više nego je poticao i stari sustav. Ako banka ili država nešto skrivaju, pretpostavlja se da to skrivaju s razlogom.
2. Kod privatnog blockchaina, entitet koji ga podiže isto tako vrti svoje čvorove (node), tj. računala koja verificiraju transakcije. Blockchain je veoma spor u pisanju podataka - transakcija se treba poslati, verificirati, i tek tada se upisuje u blockchain nakon što [blok][block] koji je sadrži biva izrudaren. Ako institucija zamijeni svoje servere nodeovima koji drže taj blockchain na životu, sve što su napravili je zamijenili svoju prijašnju brzu bazu novom vrlo sporom bazom. Ako im se desi poplava ili požar, ista računala stradaju, isti problem nastaje. Prednost u imanju svojih vlastitih blockchaina ne postoji za entitete koji nisu orijentirani na transparentnost prema javnosti. U tom slučaju, obična baza je bolja opcija.

## Zaključak

Dok naša 24-satna ideja svakako ima svojih rupa i dijelova koje bi trebalo razraditi, svrha joj je bila dokazati kako je jednostavno i bezbolno implementirati kriptovalute u postojeći sustav - bez ratova i sukoba interesa. Centralizacija nije uvijek loša, i decentralizacija nije uvijek dobra. [Deflacija i inflacija][finite] imaju svoje prednost i mane. Nije sve uvijek polarno, i da bi se neki sustav unaprijedio bitno je iz drugog uzeti ono što je dobro i izbaciti ono što je loše ili nekompatibilno.

Korporativne primjedbe na ovaj sustav dKune bile su u rangu da se korisnicima daje previše financijske slobode, i da to otvara vrata prema pranju novca, izbjegavanju poreza, i slično. No korporativni i državni igrači zaboravljaju da [čak i deterdžent][tide] može biti instrument plaćanja ako je to potrebno. Kriminalci će **uvijek** naći načina da trguju onime čime trebaju trgovati - zabrane i protjerivanja štete samo prosječnim korisnicima, a na njima se ekonomski sustav bazira, i njima je ta sloboda najpotrebnija da vrate vjeru u vladu, banke, i demokratski sustav.

Hrvatska se, s obzirom na otpor na koji smo u Bitfalls naišli do sada, neće pridružiti ovom novom tehnološkom valu još barem 5 do 10 godina. No, [ne odustajemo][blockconf] od edukacije. Možda uspijemo u namjeri da dovedemo državu u 21. stoljeće i da, za promjenu, ne kaskamo za baš svima.

[unstoppable]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/
[gold]: https://bitfalls.com/hr/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[tether]: https://bitfalls.com/hr/2017/10/21/the-curious-tale-of-tethers/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[anon]: https://bitfalls.com/hr/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[ledger]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[novathon]: http://novathon.net
[mew]: https://MyEtherWallet.com
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[tide]: http://nymag.com/news/features/tide-detergent-drugs-2013-1/
[blockconf]: http://blockconf.io
[folio]: https://bitfalls.com/hr/portfolio-management/
[cryptoruble]: https://cointelegraph.com/news/breaking-russia-issuing-cryptoruble
[emcash]: https://www.cryptocoinsnews.com/emcash-dubais-first-official-state-cryptocurrency/
[zim]: http://edition.cnn.com/2016/05/06/africa/zimbabwe-trillion-dollar-note/index.html
[block]: https://bitfalls.com/hr/glossary/#block
[tenx]: https://www.tenx.tech/
[Bitwalla]: https://www.bitwala.com/
[f2]: http://f2.bug.hr
[monaco]: https://mona.co/
[paper]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[shop]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/