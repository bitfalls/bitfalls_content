_Susrećemo se s kriptovalutama svaki dan, često bez jasne predodžbe o značenju predznaka "kripto" u nazivu. Kriptografija ima povijest, krvaviju i mutniju nego bismo u prvi mah pomislili. Ovo je dio uvoda u  računalnu kriptografiju, njenu prošlost i - moguću - budućnost._

---

Sve od vremena [Cezara](http://practicalcryptography.com/ciphers/caesar-cipher/), a vjerovatno i ranije, ratovi su se gubili i dobivali mešetarenjem tajnama. Kriptoanaliza je tisućljećima u žiži interesa obavještajnih službi.

Povjesni;ari vjeruju da je 2. svj. rat dobiven uvelike zahvaljujući Savezničkim kriptoanalitičarima. U godinama nakon 2. svj. rata, sve od 1952, američka NSA je operirala uglavnom ispod radara običnog pučanstva. Jedan od šaljivih prijevoda naziva "NSA" je bio "No Such Agency" (Nema Takve Agencije, op. prev).

![I smell a rat](../images/01.jpg)

Kada je 70-tih IBM izumio algoritam za enkripciju simetričnim ključem,  [DES](https://en.wikipedia.org/wiki/Data_Encryption_Standard), spomenuta je Agencija lobirala za usvajanje oslabljene verzije algoritma kao preporučenog standarda iza kojeg stoji država - 1977. Ovo je dovelo do usvajanja ovog (oslabljenog) standarda na međunarodnom nivou.

Obavještajni odbor US Senata u izvješću iz 1978 kaže *"[[Kod razvoja DES-a, NSA je uvjerila IBM da je smanjeni ključ dovoljan; indirektno je pomogla u razvoju S-box strukture; i zajamčila da je konačni DES algoritam, koliko oni znaju, bez ikakvih statističkih i matematičkih slabosti.\]]*(https://en.wikipedia.org/wiki/Data_Encryption_Standard#cite_note-5)" 

 John Gilmore iz [EFF](https://www.eff.org),  [komentirao je ovo](http://www.toad.com/gnu/):

"*NSA je intervenirala kod standardizacije ove sheme enkripcije u ranim 70-ima, skraćivanjem tajnih ključeva, tako da bi mogli razviti vlastite DES crackere (uređaji za probijanje enkripcije, op. prev). Ali idućih 25 godina proveli su lažući nam koliko je ova enkripcija sigurna, ne bi li nas sve ohrabrili da je koristimo - i koristili smo je. Ovo je omogućilo NSA da prisluškuje svakoga tko je koristio DES, što znači čitavu financijsku zajednicu/branšu, i većinu kompjuterskih, i mrežno-sigurnosnih sistema. Tehnologija je napredovala do točke kad svatko sa opremom od $200,000 može probiti enkripciju, izlažući tako riziku svu DES-om zaštićenu infrastrukturu*. "

EFF je potrošio $250,000 da pokaže izvedivost probijanja DES enkripcije, koja je kasnije napuštena, i zamijenjena [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) enkripcijom.

<a title="By The original uploader was Matt Crypto at English Wikipedia Later versions were uploaded by Ed g2s at en.wikipedia. [GFDL (http://www.gnu.org/copyleft/fdl.html) or CC BY 3.0 us (http://creativecommons.org/licenses/by/3.0/us/deed.en)], via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File%3ABoard300.jpg"><img width="512" alt="Board300" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Board300.jpg/512px-Board300.jpg"/></a>

_DES cracker, dizajniran od EFF-a_

Samo desetljeće kasnije, internet [pamti](http://www.nytimes.com/1994/06/12/magazine/battle-of-the-clipper-chip.html) bitku oko privatnosti za vrijeme Clintonove administracije - priču o Clipper čipu.

![MYK-78 Clipper chip](../images/03.jpg)

_MYK-78 Clipper čip, fotografija Travisa Goodspeeda [<a href="http://creativecommons.org/licenses/by/2.0">CC BY 2.0</a>], <a href="https://commons.wikimedia.org/wiki/File%3AMYK-78_Clipper_chip_markings.jpg">via Wikimedia Commons</a>_

Ukratko, NSA je, opet, gurala standard - i kriptografski čip koji bi se koristio u uređajima - kriptografski "siguran", gdje bi državni organi bili u posjedu ključeva, dostupnih po predočenju sudskog naloga.
Šira adopcija na tržišti je izostala, između ostalog i zbog closed-source kriptografskog algoritma [Skipjack](https://en.wikipedia.org/wiki/Skipjack_(cipher)), koji je naknadno deklasificiran.

Kada je 2013.-te danas slavni Edward Snowden razotkrio opseg backdoor-ova koje je NSA koristila kompromitiranjem kriptografskih standarda - javnost je to doživjela kao veliku vijest. Stručnjaci nisu. Problemi sa standardima za generatore  nasumičnih brojeva, preporučenim od strane NIST i ANSI (javni instituti za standardizaciju) su nešto [o čemu se pisalo već 2006.](https://eprint.iacr.org/2006/190), a Bruce Schneier [je pisao o ovome za Wired](https://www.wired.com/2007/11/securitymatters-1115/) 2007. *"trebali biste se zabrinuti zbog standarda za generator nasumičnih brojeva koji uključuje algoritam koji je spor, loše dizajniran, i mogao bi imati backdoor za NSA*". 

Kasnije se pokazalo da je ovaj algoritam - poznat i kao Dual Elyptic Curve Deterministic Random Bit Generator - `Dual_EC_DRBG` - bio uvelike korišten za backdoor u serverima servers / operativnim sustavima diljem svijeta, i omogućio NSA da prisluškuje komunikaciju velikog dijela zemaljske kugle.  Radilo se o **velikoj** vijesti.

Ovo samo po sebi ne bi bilo problem - svaki softver ima propuste, i kriptografski algoritmi nisu iznimka. Problem je što je državna agencija gurala ovaj algoritam - sa poznatim propustom - da bude službeno preporučen kao standard struke - za softverske i hardverske sustave, operativne sustave širom svijeta. Za osiguravanje servera, routera, firewallova. Algoritam je na kraju promoviran i međunarodno kao ISO standard.

Kasnije se pročulo da je [NSA platila RSA](http://www.reuters.com/article/us-usa-security-nsa-rsa/exclusive-nsa-infiltrated-rsa-security-more-deeply-than-thought-study-idUSBREA2U0TY20140331) - firmi pioniru komercijalne asimetrične kriptografije - 10 milijuna USD - da uključe kompromitirani algoritam u svoja softverska rješenja - i kasnije [koristila te RSA proizvode kao argument](https://en.wikipedia.org/wiki/RSA_Security#Alleged_NSA_Dual_EC_DRBG_backdoor) pri lobiranju kod [National Institute of Standards and Technology](https://en.wikipedia.org/wiki/National_Institute_of_Standards_and_Technology) - da ovo tijelo usvoji isti, problematični algoritam kao službenu preporuku (iza koje stoji država).

Prema brojnim sigurnosnim stručnjacima, ovo guranje algoritama/ generatora sa poznatim propustima, potencijalno je izložilo sisteme ne samo prisluškivanju državnih agencija, nego i hakerima koji znaju svoj posao. Ovo je povijest stavljanja želje za totalnim nadzorom iznad sigurnosti - svjesno ugrožavanje sigurnosti širokog broja sustava - samo da se dođe do što većeg broja podataka. U dokumentu u kojem se traže proračunska sredstva, NSA je sama tražila milijune - stotine milijuna USD za kompromitiranje sustava / standarda ugradnjom backdoora.

A ovo su samo one kompromitacije standarda za koje javnost do sada zna.

Ima još. Prema [članku Glenna Greenwalda](https://www.theguardian.com/books/2014/may/12/glenn-greenwald-nsa-tampers-us-internet-routers-snowden) u Guardianu iz 2014., citirajući izvještaj same NSA, Agencija rutinski presreće pošiljke mrežne opreme - firewallove, servere, routere. "Agencija onda ugrađuje backdoor nadzorne alate, prepakira pakete sa tvroničkim pečatom i šalje ih dalje."

![NSA photo of interception/repackaging of cisco routers](../images/04.jpg)

Procurjeli interni agencijski newsletter citira managera: 

*"To ovako funkcionira: pošiljke računalne mrežne opreme (serveri, routeri, itd,) koje se dostavljaju našim metama širom svijeta se **presreću**. Nadalje, **preusmjeravamo ih na tajnu lokaciju** gdje zaposlenici TLA/AO  (AO-S326) odjela, uz podršku Remote Operations Centra (S321), omogućuju **instalaciju sklopova za nadzor** direktno u elektronsku opremu naših meta. Ova se oprema onda prepakira i vraća natrag u tranzit. Sve se ovo odrađuje uz pomoć naših partnera u obavještajnoj zajednici i tehničkih stručnjaka u TAO."*

U jednom od budućih članaka planiramo istražiti detaljnije opseg nadzora kojem smo svakodnevno podvrgnuti.

Dakle, kada je Agencija predložila par block kriptografskih algoritama zamišljenih primarno za IOT odnosno hardver sa oskudnim resursima, 2013. godine,  i nastojala progurati njihovo usvajanje na globalnom nivou od strane ISO međunarodnog tijela za standarde, naišla je na konkretan otpor. 

Između ostalih progovora, stručnjaci su pronašli slabosti, kao u [ovom](https://www.iacr.org/workshops/fse2014/slides-09_1.pdf) izvještaju diferencijalne kriptoanalize znanstvenika sa  Bauhaus sveučilišta u Weimaru iz 2014.

Dio američke delegacije pri ISO'u je uključivao i službenike NSA. Protivnici, Japaneski, Njemački i Izraelski delegati pri ISO-u, kriptografski stručnjaci, izrazili su rezerviranost glede ovih algoritama. Došlo je do neslaganja kod razgovora u Jaipuru u Indiji 2015., u Abu Dhabiju 2016., i u Hamiltonuna Novom Zelandu ove godine. 

Kako nisu mogli postići 2/3 konsenzus, američka delegacija je na kraju odustala od najslabijih verzija algoritama u svom prijedlogu, gurajući usvajanje "najrobusnijih" verzija ovih algoritama, proguravši prijedlog na konačno glasanje u Veljači 2018.

Japan, Njemačka i Izrael ostaju protiv.
