### Uvod : internet je konceptualno zastranio

Kada je započeo, internet je predstavljao predivno obećanje o decentralizaciji i demokratizaciji znanja i informacija, kako u smislu konzumacije, tako i u smislu izdavaštva. Prije interneta, trebalo je imati novinsku ili televizijsku / radijsku kuću - ili izdavačku tvrtku pod svojom kontrolom, da bi mogli svoju poruku donijeti pred širu javnost. Isto je vrijedilo za glazbu / videa. 
Objaviti vlastitu glazbu ili vieo uratke, i staviti ih pred oči i uši globalne publike podrazumijevalo je da ste morali imati ***resurse***.

Internet je ovo radikalno promijenio.

Danas, ako netko ima kvalitetan sadržaj, i malo tehničkog znanja - ili skromna sredstva na raspolaganju - može taj sadržaj učiniti dostupnim svakome sa pristupom internetu, širom svijeta.
Informacije su postale demokratizirane. Znanje je postalo dostupno. Isto vrijedi i za izdavaštvo. Danas, anonimni zviždači povjerljivih političkih informacija mogu očekivati da će promijeniti ishod izbora, bez obzira na to tko je od političkih igrača "kupio" mainstream medije.
To je veća i slobodnija protočnost informacija nego ikad u povijesti.

Možemo slobodno reći da je internet promijenio stvari za našu civilizaciju u istoj mjeri kao i Gutenbergov izum tiskarskog stroja.

Ali, stvari ipak nisu idealne. Sa masovnim širenjem interneta došao je krupniji kapital, a sa njme i monopoli, i centralizacija upravljanja privatnih podataka korisnika, i kontrole nad informacijama. Ovo je uvelike centralizacija do koje je došlo zbog tehničkih razloga i efikasnosti, ne nekakvom prisilom, a za to možemo zahvaliti trenutnoj strukturi internetskih protokola. Konkretno, [HTTP protokol](https://hr.wikipedia.org/wiki/HTTP) sa svojim klijent-server modelom, DNS-IP routingom i adresiranjem sadržaja.

***Na ovoj slici - jedan od prvih web servera, vlasništvo Tim Berners-Lee-a, sa ceduljom "Ovaj stroj je server. Ne gasiti!!!"***

![web server, T. Berners Lee](../images/01.jpg)



Internet je zastranio. Turska vlada je blokirala pristup Wikipediji u travnju 2017. jer je Wikipedia odbila izbrisati članak koji je tvrdio umješanost Turske u sponzoriranje Al-Qaede i ISIL-a. Blokada još traje. Vlada NR Kine je blokirala pristup oko jedne petine planete stranicama poput BBC-ja, YouTubea, Facebooka, Twittera, Amnesty International, i mnogih, mnogih drugih. Ta je blokada dobila naziv "Veliki kineski vatrozid".

Godine 2016. i 2017.  dogodili su se veliki padovi sistema na internetu, zbog DDOS napada i ljudskih pogreški u data-centrima, usljed kojih su veliki dijelovi interneta imali problema sa funkcioniranjem. Ovi su događaji inzijali na vidjelo koliko se oslanjamo na velike pružatelje usluga, kao Amazon AWS, CDN-ove, DNS providere....

Kao korisnici interneta, ovisimo o sadržaju pohranjenom u određenim data-centrima, u određenim državama, iza određenih međunarodnih parica / kablova. Ovi padovi sistema su bili mogući zbog strukture mreže.



![Wikipedia Turkey logo](../images/02.svg)

**Slika iznad - logotip Turske Wikipedije**

A nismo ni počeli pričati o cenzuri, zapljenama servera, itd.

Naš centralizirani model pohrane podataka, do neke male mjere ublažen CDN servisima, je odgovoran za velika rasipanja bandwidtha, i velike gubitke brzine zbog mrežne latencije. Ako je, npr, izvorišni podatkovni centar fizički dosta udaljen, biti će očito sporije učitavanje sadržaja i sporiji protok podataka.

### Ovisni smo o  centralnim internet kablovima / paricama

Kada pristupamo sadržaju hostanom na serveru na drugom kontinentu, oslanjamo se na jednu - ili nekoliko međunarodnih internetskih parica za pristup stranicama / podacima - pošto je sadržaj pohranjen na jednoj lokaciji. Neki veći igrači na internetu imaju podatkovne centre širom planete, ali i ovo dokazuje da je internet promašio svoj cilj - decentralizaciju, dostupnost i demokratizaciju konzumacije i objavljivanja sadržaja.

### Oslanjamo se na hosting providere

Naš je sadržaj pohranjen na serverima hosting firmi (cloud provideri samo zamagljuju taj detalj ). Ako ta hosting kompanija, ili njeni podatkovni centri, ili severi, odu offline - i naš sadržaj je offline. Štoviše, ako hosting kompanija odluči skinuti sadržajk s weba - oni su to u mogućnosti napraviti.

### Naš sadržaj je lagan plijen

Pod trenutnim modelom, naš sadržaj / resursi / informacije / znanje su inherentno podložni cenzuri, ugasivi, i kvarljivi. 
Hakeri mijenjaju i infiltriraju web stranice tako često, da to više i nije vijest. Državna cenzura je također nešto što se viđa često. [Archive.org](http://web.archive.org/) je napravio vrstu muzeja interneta za protekle itnernetske godine, ali potreban nam je internet otporan na sve vrste "kvarljivosti" podataka.

![Burning of Alexandria, by Hermann Goll, 1876](../images/03.jpg)

**Slika iznad - palež Aleksandrije, Hermann Goll, 1876.**

Mogli bismo reći da, u sadašnjem trenutku naše civilizacije ne bismo trebali tolerirati jednu (ili nekoliko) kritičnih točki o kojima bi ovisio cjelokupan pristup internetu - koji je postao leksikon svog ljudskog znanja.

## ...i tu dolazimo do IPFS-a.

IPFS, ili Inteplanetarni podatkovni sustav je open-source projekt za koji je zaslužna tvrtka Protocol Labs, koju je 2014. osnovao Juan Benet. IPFS je projekat koji uvodi duboke inovacije. Možda najbliži projekti koje možemo usporediti sa IPFS-om su [Freenet](https://freenetproject.org), i Bittorrent. IPFS si je uzeo za cilj izmijeniti internet na nivou protokola.

Da bi se ovo postiglo, kombiniraju se tehnološka dostignuća Bittorrenta, Git-a, kriptografskog sažimanja (hashing), Kademlia DHT (distribuirane hash tablice), s ciljem temeljitog redefiniranje internetske komunikacije.

### IPFS decentralizira pohranu

Ovo znači da svaki kompjuter spojen na mrežu može biti server. Pohrana je decentralizirana i distribuirana. Pošto objekti / sadržaj - nisu adresirani po ciljnoj IP adresi, nema potrebe za statičkim IP adresama. Ovo eliminira potrebu za dediciranim podatkovnim centrima, i umanjuje ovisnost o hosting tvrtkama.

### IPFS adresira objekte po sadržaju, a ne lokaciji.

Ovo znači da je sadržaj adresiran po svom kriptografskom hashu - šifri. Ta šifra je jedinstvena s obzirom na sadržaj (datoteke, web stranice, itd) - za razliku od trenutnog modela, koji je vezan za IP adresu servera. Ako usporedimo trenutni model interneta sa adresiranjem knjiga po fizičkoj adresi knjižnice, i broju police na kojoj se knjiga nalazi, onda IPFS ide na to da knjigu adresira / imenuje po njenom naslovu.

Ovo adresiranje po sadržaju - kriptografskim šiframa - osigurava vjerodostojnost podataka, jer ako bi se i jedno slovo ili znak u datoteci promijenio, šifra odnosno hash za taj sadržaj su je potpuno drukčiji. Ovo otvara mogućnost dohvaćanja različitih verzija sadržaja na način na koji to radi Git sa svojim commit sustavom. Vraćanje na prethdnu verziju, transparentnost izmjena, imutabilnost postaju dostupni za ovaj model.

Ovo također znači da možemo imati distribuciju sadržaja efikasnu kao CDN servisi, ako ne i bolju, jer se sadržaj može keširati na stotinama ili tisućama petlji diljem interneta, osiguravajući visoku dostupnost - s kojom možemo pristupati istom sadržaju, sa istom oznakom bez obzira *odakle* ga dohvaćamo - čak i da je pola interneta offline. Pod ovim modelom, zaobilaženje Turske cenzure Wikipedije postaje dječja igra. Korisnici mogu lako dohvatiti isti sadržaj (sa istom adresom) sa njihovog lokalnog interneta unutar Turske, bez ijedne centralne lokacije. Svaki kompjuter na mreži, jednom kada dohvati / učita sadržaj, kao što su web stranice, može keširati isti i postati vjerodostojan izvor tog sadržaja.

Pod trenutnim modelom, ako datoteka ili "komad" sadržaja bude premješten na drugu lokaciju / server, svi linkovi na taj sadržaj se moraju mijenjati. Adresiranje po sadržaju znači da je isti sadržaj - hostan bilo gdje - premješten bilo gdje, kopiran, itd - još uvijek dostupan pod istom adresom. ***KAKO*** je odgovornost protokola.

(*Disclaimer - ne bismo trebali brkati **stalnost** - i integritet podataka /  dosljedno adresiranje po sadržaju - sa trajnošću same pohrane. [ipfs-cluster](https://github.com/ipfs/ipfs-cluster) - trenutno u alfi, sa vrlo živahnim developmentom, se bavi ovim aspektom - **"pinanjem"** - odnosno distribucijom sadržaja na više petlji / mrežnih uređaja*)

### IPFS implementira Kademlia Distribuirane Hash tablice

IPFS koristi algoritam sličan Bittorrentu - *[Distribuirane Hash Tablice](https://www.wikiwand.com/en/Distributed_hash_table)* - ***DHT*** - kojem nisu potrebne ikakve centralne točke za dohvaćanje sadržaja. Kademlia algoritam omogućava da bilo koji zahtjev za sadržajem treba maksimalno ***O(log(n))*** upita da se dođe do bilo kojeg sadržaja na mreži. Dakle - recimo da se radi o maksimalnih 30 upita za pronalaženje bilo čega na mreži od 1,000,000,000 računala. Sustav je brz. Ovo također znači da sistem nije ovisan o jednoj točki, DDOS otpornost i brzinu. Ako naš susjed u kući do nas ima keširan neki sadržaj na vlastitom uređaju, mi ga nećemo morati dohvaćati sa druge strane planeta. I nećemo se morati brinuti da li je taj susjed nekako izmijenio datoteku koja nam treba.

Glavni dio posla na razvoju IPFS-a, kako je Juan Benet objasnio u  [prezentaciji na sveučilištu Stanford](https://www.youtube.com/watch?v=HUVmypx9HGI) - nije na samom protokolu i njegovim algoritmima - nego na integraciji / kompatibilnosti IPFS-a s trenutnim modelom interneta. Na primjer, radi se na tome da se **adresiranje po sadržaju** integrira u postojeće internetske preglednike. Ili - rad na integraciji IPFS pohrane / protokola sa postojećim datotečnim sustavima preko [FUSE interfacea](https://en.wikipedia.org/wiki/Filesystem_in_Userspace) (tako da pristup IPFS-u ne bude ograničen samo na internet preglednike). Najveći dio posla je postizanje bezbolnog prelaza / adopcije IPFS-a kod korisnika.

### IPFS može funkcionirati na više transportnih protokola 

IPFS je tu fleksibilan, pa može koristiti TCP, UDT ili Bluetooth. Ili Tor i onion-routing, za potrebe anonimnosti. Zajedno sa Kademlia odnosno DHT protokolom, ovo omogućava razvoj aplikacija otpornih na cenzuru - sposobnih da funkcioniraju "ispod radara". Implikacije ovih dviju komponenti (decentralizirana arhitektura i fleksibilnost odabira protokola) su dalekosežne.

### IPFS gradi na već uspješnim protokolima

Bittorrent je sam po sebi tehnološki napredan koncept. Uspio se oteti pokušajima cenzure i pokazao se otporan na pokušaje da ga se ugasi. Decentralizirani Bittorrent protokol nije jednostavno srušiti ni krupnim igračima poput država. 
Tu IPFS "gradi na ramenima" dokazano uspješnih projekata. Razlika je u tome što IPFS ima skroz drukčije ciljeve.

Na primjer - kod Bittorrenta sadržaj je upakiran u pakete, koje onda downloadamo u manjim dijelovima. Ali adresiranje i uspoređivanje sadržaja je na nivou paketa (može se raditi o folderima sa mnoštvom datoteka). IPFS adresira sadržaj na nivou block-ova - dakle, teoretski, dohvaćanje jquery javascript datoteke / libraryja bi bilo moguće sa nečijeg tableta u susjednoj prostoriji, umjesto sa udaljenog podatkovnog centra. Ova atomiziranost IPFS protokola omogućava [goleme uštede pri pohrani](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6).

Isto tako, dok Bittorrent razdvaja same podatke i metadata ("podatke o podacima"), zahtjevajući poseban layer za tracking torrenta, IPFS gleda pružiti dosta kompletnije rješenje, odnosno paket rješenja.

Da citiramo IPFS whitepaper, 

> *Za razliku od BitTorrenta, BitSwap se ne ograničava na blokove u jednom torrentu. BitSwap funkcionira kao tržnica blokova, gdje petlja može doći do potrebnih blokova, bez obzira na to kojih su datoteka ti blokovi dio. Blokovi mogu doći iz potpuno nepovezanih datoteka u sustavu. Petlje (uređaji) dolaze na ovo tržište da bi razmjenjivale potrebne blokove*

Implikacije ovoga znače puno efikasniji internet. Na primjer, ako je naš susjed u kući do, već učitao neki sadržaj, isti može biti i  nama dostupan, tako da 40% (ili više) tražene web stranice / sadržaja dohvaćamo ne iz udaljenog podatkovnog centra - nego doslovno iz kuće do.

**[Bitswap](https://github.com/ipfs/go-ipfs/tree/master/exchange/bitswap)** je ipfs modul zadužen za ove "tržne" mehanizme za razmjenu blokova, i u planu razvoja ima lako dostupnu mogućnost keširanja sadržaja za druge korisnike mreže. Po defaultu, nikakav sadržaj koji kao petlja nismo skinuli sa mreže, neće biti keširan na našem uređaju.

Prema [ipfs često postavljanim pitanjma](https://github.com/ipfs/faq/issues/47), 

> *...po standardnim postavkama IPFS neće dohvatiti ništa što eksplicitno niste zahtijevali ... protokoli povrh IPFS-a mogu dohvaćati datoteke za potrebe mreže, ali ovo je opcionalno, i tek moguća nadgradnja same IPFS mreže. Primjeri su bitswap agenti, [ipfs-cluster](https://github.com/ipfs/ipfs-cluster), i [Filecoin](http://filecoin.io/).*



### IPFS otvara vrata cloud-computingu kakav je idealno zamišljen

To znači otporan, lako dostupan sadržaj sa redundantnom arhitekturom, koja obećava visoku dostupnost i nisku latenciju. 

Jedan od open-source "plodova" IPFS-a je [libp2p](https://libp2p.io/) - MIT-licenciran skup library-ja za swarm, p2p sustave. IPFS je projekat koji je u izradi, ali dosta obećava - i nije tek puko teoretiziranje.

U kolovozu i rujnu ove godine [odvijao se najveći ICO do sada](https://www.coindesk.com/257-million-filecoin-breaks-time-record-ico-funding/), i projekat je skupio rekordnih 260,000,000 USD. Radilo se o ICO prodaji Filecoina, tokena aplikacije koja gradi na IPFS protokolu, od kompanije Protocol Labs. Vrijedi spomenuti da tih 260 milijuna nisu svi prikupljeni javnom prodajom tokena neinformiranim masama, [52 milijuna su prikupljeni od VC-a, u pretprodaji](https://www.coindesk.com/filecoin-presale-raises-52-million-ahead-ico-launch/), a za njih mođemo pretpostaviti da su ynali u što su se upuštali.

Dakle, moglo bi biti nešto od projekta.

![OpenBazaar repos on github](../images/04.jpg)



Još jedan projekat koji gradi na IPFS-u je [OpenBazaar](https://www.openbazaar.org/). Za one koji ne znaju, OpenBazaar je pionir decentraliziranog interneta, jedan od gotovih proiyvoda koji na ovom području gaze u budućnost. Radi se o decentraliziranom, p2p marketplace-u, ecommerce projektu na kojem svatko može, bez ikakvih davanja, otvoriti ecommerce shop, i prodavati proizvode za kriptovalute.
Projekat je već odmakao u razvoju (trenutno je u verziji 2.0), i prilično glatko funkcionira. I koristi IPFS za pohranu.

Još jedan projekat u fazi produkcije je [Steemit](https://steemit.com) - koji planira koristiti IPFS za pohranu datoteka.

[Digix](https://digix.global/) je još jedan startup baziran na blockchainu / token sa tržišnom kapitalizacijom od 130,000,000 USD u trenutku pisanja članka. Iymeđu ostalih tehnologija, koristi i IPFS.

[Mediachain](http://www.mediachain.io/) je još jedan blockchain projekat koji koristi IPFS.

Zatim Orbit - distribuirana, peer-to-peer chat applikacija sagrađena povrh IPFS-a - projekt je dalje urodio nekim zanimljivim FOSS pod-projektima poput - [orbit-db](https://github.com/orbitdb/orbit-db) - "distribuirane peer-to-peer baze podataka za decentralizirani web".  Orbit možete pogledati [ovdje](https://orbit.chat/#/connect).

Lista se nastavlja, neke od projekata možete naći [ovdje](https://github.com/ipfs/awesome-ipfs).

Prije koju godinu, [netko je kopirao](https://discuss.ipfs.io/t/ipfs-vs-webtorrent-what-the-value-of-using-ipfs-instead-of-torrent-files/64/6) čitav [cdnjs](https://cdnjs.com/) na IPFS, i pri tome uspio smanjiti cjelokupnu pohranu sa 70-i-nešto Gb na 30-i-nešto - zahvaljujući atomiziranoj de-duplikaciji koju pruža IPFS. Ima i projekata poput [nacrta implementacija Hadoopa](http://www.cse.unsw.edu.au/~hpaik/thesis/showcases/16s2/scott_brisbane.pdf) povrh IPFS-a, koji obećava konkretna ubrzanja. Niču i mnogi drugi projekti, koji kombiniraju Ethereum blockchain kao računalni layer, i IPFS kao layer za pohranu.

IPFS je projekat zamišljen na nivou *protokola* - tako da ostavlja mnoga pitanja - poput poticaja korisnicima za pružanje prostora za pohranu - aplikacijama koje grade povrh ovog protokola da pronađu odgovore. IPFS specifikacija je još uvijek u procesu evoluiranja.

***U ovom članku, pokušali smo čitatelje upoznati sa osnovnim pojmovima IPFS-a - jednog od projekata koji rade na internetu sutrašnjice.***
***Nadamo se pokriti više tehničkih detalja - poput IPNS-a, ipfs-clustera, Bitswap modula - i neke od aplikacijakoje grade na IPFS-u - u nekim od budućih članaka.***

