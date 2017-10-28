*Napomena: tehnički uvod koji slijedi je koristan svima, no namijenjen je prvenstveno ne-početničkoj IT publici.*

---

Kada je započeo, internet je predstavljao predivno obećanje o decentralizaciji i demokratizaciji znanja i informacija, kako u smislu konzumacije, tako i u smislu izdavaštva. Prije interneta, trebalo je imati novinsku ili televizijsku / radijsku kuću - ili izdavačku tvrtku pod svojom kontrolom, da bi mogli svoju poruku donijeti pred širu javnost. Isto je vrijedilo za glazbu / video. Objaviti vlastitu glazbu ili video uratke i staviti ih pred oči i uši globalne publike podrazumijevalo je da ste morali imati pozamašne **resurse**.

Internet je to radikalno promijenio.

## Struktura Interneta

Danas ako netko ima kvalitetan sadržaj i malo tehničkog znanja - ili skromna sredstva na raspolaganju - može taj sadržaj učiniti dostupnim svakome sa pristupom internetu diljem svijeta.

Informacije su postale demokratizirane. Znanje je postalo dostupno. Isto vrijedi i za izdavaštvo. Anonimni zviždači povjerljivih političkih informacija mogu očekivati da će promijeniti ishod političkih izbora, bez obzira na to tko je od političkih igrača "kupio" medije.

To je veća i slobodnija protočnost informacija nego ikad u povijesti.

Možemo slobodno reći da je internet promijenio stvari za našu civilizaciju u istoj mjeri kao i Gutenbergov izum tiskarskog stroja.

Ali stvari ipak nisu idealne. Sa masovnim širenjem interneta došao je krupniji kapital, a sa njime i monopoli i centralizacija upravljanja privatnim podacima korisnika, i kontrole nad informacijama. Do te je centralizacije uvelike došlo zbog tehničkih razloga i efikasnosti, ne nekakvom prisilom, a za to možemo zahvaliti trenutnoj strukturi internetskih protokola. Konkretno, [HTTP protokol](https://hr.wikipedia.org/wiki/HTTP) sa svojim klijent-server modelom, DNS-IP routingom i adresiranjem sadržaja.

***Na ovoj slici - jedan od prvih web servera, vlasništvo Tim Berners-Lee-a, sa ceduljom "Ovaj stroj je server. Ne gasiti!!!"***

![web server, T. Berners Lee](../images/01.jpg)



Internet je zastranio. Turska vlada je blokirala pristup Wikipediji u travnju 2017. jer je Wikipedia odbila izbrisati članak koji je tvrdio umješanost Turske u sponzoriranje Al-Qaede i ISIL-a. Blokada još traje. Vlada NR Kine je blokirala pristup jednoj petini ljudskog stanovništva stranicama poput BBC-a, YouTubea, Facebooka, Twittera, Amnesty International, i mnogih, mnogih drugih. Ta je blokada dobila naziv "Veliki kineski vatrozid".

Godine 2016. i 2017. dogodili su se veliki padovi sistema na internetu zbog DDOS napada i ljudskih pogreški u data-centrima, usljed kojih su veliki dijelovi interneta imali problema sa funkcioniranjem. Ovi su događaji učinili očitim koliko se oslanjamo na velike pružatelje usluga poput Amazon AWS, CDN-ova, DNS providera...

Kao korisnici interneta, ovisimo o sadržaju pohranjenom u određenim data-centrima, u određenim državama, iza određenih međunarodnih parica / kablova. Ovi padovi sistema su bili mogući zbog strukture mreže.



![Wikipedia Turkey logo](../images/02.svg)

A da ni ne spominjemo cenzuru, zapljene servera, itd.

Naš centralizirani model pohrane podataka, do neke male mjere ublažen CDN servisima, je odgovoran za velika rasipanja bandwidtha, i velike gubitke brzine zbog mrežne latencije. Ako je, primjerice, izvorni podatkovni centar fizički dosta udaljen, učitavanje sadržaja i protok podataka biti će očito sporiji.

### Ovisni smo o centraliziranoj infrastrukturi

Kada pristupamo sadržaju na serveru na drugom kontinentu, oslanjamo se na jednu ili nekoliko međunarodnih internetskih parica za pristup stranicama / podacima - pošto je sadržaj pohranjen na jednoj lokaciji. Neki veći igrači na internetu imaju podatkovne centre širom svijeta, ali i ovo dokazuje da je internet promašio svoj cilj - decentralizaciju, dostupnost i demokratizaciju konzumacije i objavljivanja sadržaja.

### Oslanjamo se na pružače web prostora

Naš je sadržaj pohranjen na serverima hosting firmi (cloud provideri samo zamagljuju taj detalj). Ako ta hosting kompanija ili njeni podatkovni centri izgube vezu - i naš sadržaj nestaje. Štoviše, ako hosting kompanija odluči skinuti sadržaj s weba - oni su to u mogućnosti napraviti.

### Naš sadržaj je lagan plijen

Pod trenutnim modelom, naš sadržaj / resursi / informacije / znanje su inherentno podložni cenzuri, ugasivi, i kvarljivi. 
Hakeri mijenjaju i infiltriraju web stranice tako često, da to više i nije vijest. Državna cenzura je također nešto što se viđa često. [Archive.org](http://web.archive.org/) je napravio vrstu muzeja interneta za protekle internetske godine, ali potreban nam je internet otporan na sve vrste korupcije podataka.

![Palež Aleksandrije, Hermann Goll, 1876](../images/03.jpg)

Ne bismo trebali tolerirati jednu (ili nekoliko) kritičnih točki o kojima ovisi cjelokupan pristup internetu. Ipak je internet postao leksikon svog ljudskog znanja.

Internet kao takav je konceptualno zastranio.

## Tu dolazi IPFS

IPFS, ili Inteplanetarni podatkovni sustav je projekt otvorenog koda (_open source_) za koji je zaslužna tvrtka Protocol Labs, koju je 2014. osnovao Juan Benet. IPFS je projekat koji uvodi istinske inovacije - možda najsličniji projekti koje možemo usporediti sa IPFS-om su [Freenet](https://freenetproject.org), i Bittorrent. IPFS si je uzeo za cilj izmijeniti internet na nivou protokola.

Da bi se ovo postiglo, kombiniraju se tehnološka dostignuća Bittorrenta, Git-a, kriptografskog sažimanja ([hashing](https://bitfalls.com/hr/glossary/#hash)), Kademlia DHT (distribuirane hash tablice), itd. s ciljem temeljitog redefiniranja internetske komunikacije.

### IPFS decentralizira pohranu

Svako računalo spojeno na mrežu može biti server. Pohrana je decentralizirana i distribuirana. Pošto objekti / sadržaj - nisu adresirani po ciljnoj IP adresi, nema potrebe za statičkim IP adresama. Ovo eliminira potrebu za posebno dodijeljenim podatkovnim centrima, i umanjuje ovisnost o hosting tvrtkama.

### IPFS adresira objekte po sadržaju, a ne lokaciji

Sadržaj je adresiran po svom [kriptografskom hashu](https://bitfalls.com/hr/glossary/#hash) - šifri. Ta šifra je jedinstvena s obzirom na sadržaj (datoteke, web stranice, itd.) - za razliku od trenutnog modela, koji je vezan za IP adresu servera. Ako usporedimo trenutni model interneta sa adresiranjem knjiga po fizičkoj adresi knjižnice, i broju police na kojoj se knjiga nalazi, onda IPFS ide na to da knjigu adresira / imenuje i traži po njenom naslovu, ne njenoj lokaciji.

Ovo adresiranje po sadržaju kriptografskim šiframa osigurava vjerodostojnost podataka, jer ako bi se i jedno slovo ili znak u datoteci promijenio, šifra odnosno hash za taj sadržaj je potpuno drukčiji. Ovo otvara mogućnost dohvaćanja različitih verzija sadržaja na način na koji to radi Git sa svojim commit sustavom. Vraćanje na prethodnu verziju, transparentnost izmjena, i nepromijenjivost postaju dostupni u ovom modelu.

Ovo također znači da možemo imati distribuciju sadržaja efikasnu kao kod CDN servisa, ako ne i bolju, jer se sadržaj može spremiti na stotinama ili tisućama petlji diljem interneta, osiguravajući visoku dostupnost. Možemo pristupati istom sadržaju sa istom oznakom bez obzira na to *odakle* ga dohvaćamo - čak i da je pola interneta izgubilo povezivost. Pod ovim modelom, zaobilaženje turske cenzure Wikipedije postaje dječja igra. Korisnici mogu lako dohvatiti isti sadržaj (sa istom adresom) sa njihovog lokalnog interneta unutar Turske, bez ijedne centralne lokacije. Svako računalo na mreži jednom kada dohvati / učita sadržaj poput web stranice, može keširati (spremiti za kasnije) isti i postati vjerodostojan izvor tog sadržaja.

Pod trenutnim modelom, ako datoteka ili "komad" sadržaja bude premješten na drugu lokaciju / server, svi linkovi/poveznice na taj sadržaj se moraju mijenjati. S druge strane, adresiranje po sadržaju znači da je isti sadržaj - spremljen ili premješten bilo kamo - još uvijek dostupan pod istom adresom. **KAKO** je odgovornost protokola.

(*Napomena - ne smijemo brkati **trajnost** i integritet podataka ili dosljedno adresiranje po sadržaju sa trajnošću same pohrane. [ipfs-cluster](https://github.com/ipfs/ipfs-cluster) - trenutno u testnom stanju, sa vrlo aktivnim razvojem, se bavi ovim aspektom - **"pinanjem"** - odnosno distribucijom sadržaja na više petlji / mrežnih uređaja*)

### IPFS implementira Kademlia Distribuirane Hash tablice

IPFS koristi algoritam sličan Bittorrentu - *[Distribuirane Hash Tablice](https://www.wikiwand.com/en/Distributed_hash_table)* - ***DHT*** - kojem nisu potrebne nikakve centralne točke za dohvaćanje sadržaja. Kademlia algoritam omogućava da bilo koji zahtjev za sadržajem treba maksimalno `O(log(n))` upita da se dođe do bilo kojeg sadržaja na mreži. Npr. radi se o cca maksimalnih 30 upita za pronalaženje bilo čega na mreži od 1,000,000,000 računala. Sustav je brz. Ovo također znači da sistem nije ovisan o jednoj točki, te da ima i DDOS otpornost i brzinu. Ako susjed u kući do nas ima keširan neki sadržaj na vlastitom uređaju, mi ga nećemo morati dohvaćati sa druge strane planeta i nećemo se morati brinuti je li taj susjed nekako izmijenio datoteku koja nam treba.

Glavni dio posla na razvoju IPFS-a, kako je Juan Benet objasnio u  [prezentaciji na sveučilištu Stanford](https://www.youtube.com/watch?v=HUVmypx9HGI) - nije na samom protokolu i njegovim algoritmima - nego na integraciji / kompatibilnosti IPFS-a s trenutnim modelom interneta. Na primjer, radi se na tome da se **adresiranje po sadržaju** integrira u postojeće internetske preglednike. Ili - rad na integraciji IPFS pohrane / protokola sa postojećim datotečnim sustavima preko [FUSE interfacea](https://en.wikipedia.org/wiki/Filesystem_in_Userspace) (tako da pristup IPFS-u ne bude ograničen samo na internet preglednike). Najveći dio posla je postizanje bezbolnog prelaza / adopcije IPFS-a kod prosječhnih korisnika.

### IPFS može funkcionirati na više transportnih protokola 

IPFS je tu fleksibilan, pa može koristiti TCP, UDT ili Bluetooth. U obzir dolaze i Tor i onion-routing, za potrebe anonimnosti. Zajedno sa Kademlia odnosno DHT protokolom, ovo omogućava razvoj aplikacija otpornih na cenzuru - sposobnih da funkcioniraju "ispod radara". Implikacije ovih dviju komponenti (decentralizirana arhitektura i fleksibilnost odabira protokola) su dalekosežne.

### IPFS gradi na već uspješnim protokolima

Bittorrent je sam po sebi tehnološki napredan koncept. Uspio se oteti pokušajima cenzure i pokazao se otporan na pokušaje da ga se ugasi. Decentralizirani Bittorrent protokol nije jednostavno srušiti ni krupnim igračima poput država. 

Tu IPFS "gradi na ramenima" dokazano uspješnih projekata. Razlika je u tome što IPFS ima skroz drukčije ciljeve.

Na primjer - kod Bittorrenta sadržaj je upakiran u pakete, koje onda preuzimamo u manjim dijelovima. Ali adresiranje i uspoređivanje sadržaja je na nivou paketa (može se raditi o folderima sa mnoštvom datoteka). IPFS adresira sadržaj na nivou block-ova - dakle, teoretski, dohvaćanje jQuery javascript datoteke bi bilo moguće sa nečijeg tableta u susjednoj prostoriji, umjesto sa udaljenog podatkovnog centra. Ova atomiziranost IPFS protokola omogućava [goleme uštede pri pohrani](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6).

Isto tako, dok Bittorrent razdvaja same podatke i metadata ("podatke o podacima"), zahtjevajući poseban sloj za praćenje torrent datoteke, IPFS gleda pružiti dosta kompletnije rješenje, odnosno paket rješenja.

Da citiramo IPFS whitepaper, 

> *Za razliku od BitTorrenta, BitSwap se ne ograničava na blokove u jednom torrentu. BitSwap funkcionira kao tržnica blokova, gdje petlja može doći do potrebnih blokova, bez obzira na to kojih su datoteka ti blokovi dio. Blokovi mogu doći iz potpuno nepovezanih datoteka u sustavu. Petlje (uređaji) dolaze na ovo tržište da bi razmjenjivale potrebne blokove*

Ovo znači puno efikasniji internet. Na primjer, ako je naš susjed u kući do već učitao neki sadržaj, isti može biti i nama dostupan, tako da 40% (ili više) tražene web stranice / sadržaja dohvaćamo ne iz udaljenog podatkovnog centra - nego doslovno iz kuće do.

**[Bitswap](https://github.com/ipfs/go-ipfs/tree/master/exchange/bitswap)** je IPFS modul zadužen za ove tržišne mehanizme za razmjenu blokova, i u planu razvoja ima lako dostupnu mogućnost keširanja sadržaja za druge korisnike mreže. U standardnim postavkama, nikakav sadržaj koji kao petlja nismo izričito skinuli sa mreže neće biti keširan na našem uređaju za druge.

Prema [IPFS često postavljanim pitanjma](https://github.com/ipfs/faq/issues/47), 

> *...po standardnim postavkama IPFS neće dohvatiti ništa što eksplicitno niste zahtijevali ... protokoli povrh IPFS-a mogu dohvaćati datoteke za potrebe mreže, ali ovo je opcionalno, i tek moguća nadgradnja same IPFS mreže. Primjeri su bitswap agenti, [ipfs-cluster](https://github.com/ipfs/ipfs-cluster), i [Filecoin](http://filecoin.io/).*

### IPFS otvara put do pravog cloud-computinga

To znači otporan, lako dostupan sadržaj sa redundantnom arhitekturom, koja obećaje visoku dostupnost i nisku latenciju. 

Jedan od open-source "plodova" IPFS-a je [libp2p](https://libp2p.io/) - MIT-licenciran skup biblioteka za swarm, p2p sustave. IPFS je projekt koji je u izradi i mnogo toga obećava - ali nije tek puko teoretiziranje.

U kolovozu i rujnu ove godine [odvio se najveći ICO do sada](https://www.coindesk.com/257-million-filecoin-breaks-time-record-ico-funding/), projekt koji je skupio rekordnih 260 miljuna dolara. Radilo se o ICO prodaji Filecoina, tokena aplikacije koja se gradi na IPFS protokolu, od kompanije Protocol Labs. Vrijedi spomenuti da tih 260 milijuna nije u cijelosti prikupljeno javnom prodajom tokena neinformiranim masama, već je [52 milijuna prikupljeno od VC-a, u pretprodaji](https://www.coindesk.com/filecoin-presale-raises-52-million-ahead-ico-launch/), a za njih možemo pretpostaviti da su znali u što su se upuštali.


![OpenBazaar repos on github](../images/04.jpg)



Još jedan projekt koji gradi na IPFS-u je [OpenBazaar](https://www.openbazaar.org/). Za one koji ne znaju, OpenBazaar je pionir decentraliziranog interneta, jedan od gotovih proizvoda koji na ovom području koračaju u budućnost. Radi se o decentraliziranoj p2p tržnici na kojoj svatko može, bez ikakvih davanja, otvoriti online dućan, i prodavati proizvode za kriptovalute.

Projekt je već odmakao u razvoju (trenutno je u verziji 2.0), i prilično glatko funkcionira, a koristi IPFS za pohranu.

Još jedan projekt u fazi produkcije je [Steemit](https://steemit.com) - koji planira koristiti IPFS za pohranu datoteka.

[Digix](https://digix.global/) je još jedan startup baziran na [blockchainu](https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/) / token sa tržišnom kapitalizacijom od 130,000,000 USD u trenutku pisanja članka. Između ostalih tehnologija, koristi i IPFS.

[Mediachain](http://www.mediachain.io/) je još jedan blockchain projekat koji koristi IPFS.

Orbit - distribuirana, peer-to-peer chat applikacija sagrađena povrh IPFS-a - projekt koji je dalje urodio nekim zanimljivim FOSS projektima poput [orbit-db](https://github.com/orbitdb/orbit-db) - "distribuirane peer-to-peer baze podataka za decentralizirani web".  Orbit možete pogledati [ovdje](https://orbit.chat/#/connect).

Lista se nastavlja, neke od projekata možete naći [ovdje](https://github.com/ipfs/awesome-ipfs).

Prije koju godinu, [netko je kopirao](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6) čitav [cdnjs](https://cdnjs.com/) na IPFS, i pri tome uspio smanjiti cjelokupnu pohranu sa 70+ Gb na 30-ak - zahvaljujući atomiziranoj de-duplikaciji koju pruža IPFS. Ima i projekata poput [implementacije Hadoopa](http://www.cse.unsw.edu.au/~hpaik/thesis/showcases/16s2/scott_brisbane.pdf) povrh IPFS-a, koji obećaje konkretna ubrzanja. Niču i mnogi drugi projekti koji kombiniraju Ethereum blockchain kao računalni sloj i IPFS kao sloj za pohranu.

## Zaključak

IPFS je projekt zamišljen na nivou *protokola* - tako da ostavlja mnoga pitanja neodgovorena - poput poticaja korisnicima za pružanje prostora za pohranu. Na aplikacijama koje grade povrh ovog protokola je da pronađu odgovore. IPFS specifikacija je još uvijek u procesu evoluiranja.

U ovom članku pokušali smo vas upoznati sa osnovnim pojmovima IPFS-a - jednog od projekata koji radi na internetu sutrašnjice. Nadamo se pokriti više tehničkih detalja - poput IPNS-a, ipfs-clustera, Bitswap modula i neke od aplikacija koje grade svoju infrastrukturu na IPFS-u u nekim od budućih članaka.