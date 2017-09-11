Jedno od najčešćih pitanja novih kripto-entuzijasta je kako hardverski [novčanici][wallet] poput [Ledger Nano S][ledger] mogu biti najsigurniji način spremanja [kriptovaluta][cc]. Što ako takav uređaj bude ukraden? Ako bude uništen? 

Ovaj članak će na tehnički (ali nadamo se i razumljiv) način objasniti kako uređaj poput Nano S radi, što točno radi, i kako je moguće da je toliko siguran a opet toliko fleksibilan.

Prije nego uronimo u objašnjenja, predlažemo da pročitate članak koji ukratko objašnjava [novčanike za kriptovalute][wallet] kako bi vam termini iz daljnjeg teksta bili čim jasniji.

## BIP

Kad se [blockchain][blockchain] pojavio kao tehnologija iza Bitcoina, a nekoj grupi programera / znanstvenika je na pamet pala nova ideja za poboljšanje bitcoin protokola, trebali su tu ideju formalizirati u obliku koji je razumljiv svim sudionicima mreže - svim korisnicima Bitcoin protokola. 

Takve formalne verzije ideja nazvale su se BIP - Bitcoin Improvement Proposal (_prijedlog za poboljšanje bitcoina_). [Svi BIPovi](https://github.com/bitcoin/bips) su javni i javno raspravljeni prije nego ih se implementira u bitcoin softver.

![Popis BIPova](https://bitfalls.com/wp-content/uploads/2017/09/01-1.png)

S tako dobrim temeljom za nove ideje, ostali [blockchainovi][blockchain] preuzeli su ono što valja, i odbacili ono što im se ne sviđa. 

_Ovdje ćemo krenuti u malo kompliciranije, tehničke vode, no molimo vas za strpljenje - sve će postati jasno do kraja članka._

Jedna od tih dobrih ideja je [BIP 39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki). BIP 39 na matematički način definira kako iz skupa od 24 običnih riječi dobiti _seed_ - nasumični broj iz kojeg se kasnije generiraju ključevi za [adrese/kripto-novčanike][wallet]. 

_**Zanimljivost**: Ako vas zanimaju popisi riječi koje je moguće koristiti, pogledajte [ovdje](https://github.com/bitcoin/bips/blob/master/bip-0039/bip-0039-wordlists.md)._

BIP 39 istovremeno definira i kako osigurati tih 24 riječi s dodatnom šifrom koja se važi kao 25. riječ. Ako se ne odabere šifra, koristi se "prazna" šifra umjesto neke prave, pa se zapravo uvijek radi o 24 riječi + šifri. 

_**Zanimljivost**: Razlika ovakve od tradicionalnih šifri na kakve ste navikli na raznim sučeljima je da prilikom upisa krive šifre u ovom slučaju nema poruke o grešci. Budući da je šifra samo još jedna riječ, _seed_ koji se dobiva iz kombinacije 24 riječi i netočne šifre je također potpuno validan. To nam koristi kod _plausible deniability_ (uvjerljivo poricanje), što ćemo objasniti kasnije - ukratko, kod osobne zaštite u slučaju pljačke._

Iz tog _seed_ broja generira se _root key_ (**glavni ključ** - kombinacija brojki i slova) za svaku kriptovalutu tj. za svaki zasebni [blockchain][blockchain]. Svaki blockchain ima svoju matematičku formulu za generiranje glavnog ključa iz seeda - na primjer kod Bitcoina je to [BIP 32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki), i on rezultira ključem poput ovog: `xprv9s21ZrQH143K3QTDL4LXw2F7HEK3wJUD2nW2nRk4stbPy6cq3jPPqjiChkVvvNKmPGJxWUtg6LnF5kejMRNNU3TGtRBeJgk33yuGBxrMPHi`. 

Iz takvog ključa se kasnije generira više privatnih ključeva koji zapravo postaju [adrese/kripto-novčanici][wallet] za pojedini blockchain.

Uf... komplicirano?

![Ilustracija zbunjenog čovjeka](https://bitfalls.com/wp-content/uploads/2017/09/02.jpg)

Dakle BIP 39 služi da odaberemo neke riječi (koje mogu biti zaštićene šifrom ili ne) iz kojih onda pomoću BIP 32 možemo generirati [adrese/kripto-novčanike][wallet].

No, kakve ovo sve ima veze s hardverskim novčanicima poput Ledgera?

## Ledger

Kada prvi put upalite Ledger, on prvo generira gore spomenuti seed: 256-bitni nasumično odabrani broj. Iz njega se izračuna gore spomenutih 24 riječi koje Ledger prikazuje na svom ekranu. 

![Ispis riječi za pohranu](https://bitfalls.com/wp-content/uploads/2017/09/04.jpg)

Korisnik tada treba zapisati te riječi na posebni papirić koji dolazi s uređajem i spremiti ga na sigurno. 

Uz to, Ledger zahtjeva i korištenje PINa koji može imati do 8 znamenki, i ukoliko je 3 puta krivo unesen, Ledger uništava sve podatke i resetira se na tvorničke postavke.

Ako se Ledger ikada uništi, izgubi, ili ukrade, originalni vlasnik papirića s riječima može ubaciti riječi u novi, rezervni Ledger, ili u neki softverski novčanik poput [MyEtherWallet][mew] i povratiti sva sredstva, jer je sve što je potrebno za ponovno generiranje _root key_-a iz kojeg se generiraju sve ostale adrese je tih 24 riječi s papira i šifra (ako je postavljena).
 
 Bitno je ponovno naglasiti da iz istog _root key_-a uvijek proizlazi isti set privatnih ključeva, tako da je za potpunu obnovu **svih** novčanika baziranih na BIP 39 sustavu dovoljno unijeti 24 riječi i šifru (ukoliko je bila postavljena) u bilo kakav softver ili hardver koji generira novčanike, i sva sredstva su vraćena.
 
### Plausible Deniability

Prije smo spomenuli zaštitu od pljačke. Evo na što se točno misli. 

Ledger ne pita za šifru prilikom prvog postavljanja 24 riječi, već naknadno kod postavljanja PINa u postavkama uređaja. 

![Proces postavljanja šifre na PIN](https://bitfalls.com/wp-content/uploads/2017/09/03-1.jpg)

U tim postavkama moguće je vezati PIN uz šifru, i tako imati 2 PINa - svaki vezan uz svoju šifru. Zbog gore spomenute činjenice da 24 riječi + šifra uvijek daju validan seed (nema nikakve poruke o grešci tipa "Netočna šifra"), lako je definirati dodatni PIN kojeg možete dati nekome tko vas, primjerice, prisiljava da predate sredstva.

U tom slučaju, unos drugog PINa neće uništiti uređaj, nego otvoriti potpuno drugi set novčanika koje tada bez grižnje savjesti možete prepustiti pljačkašu - on ne može znati je li neki PIN varka ili pravi. Za dodatnu uvjerljivost, stavite na novčanike generirane dodatnim PINom neke trivijalne iznose, i pljačkaš će biti uvjeren da se dočepao svih vaših sredstava.

### Vjerojatnosti pogotka

Mnogi se pitaju: "ali ako imamo samo 24 riječi i BIP39 ih definira 2048 ukupno, čak ne ni cijeli riječnik, kako to da nam netko ne može pogoditi kombinaciju i uzeti sredstva tako da je ukuca u svoj Ledger"?

Postoji 2^256 ili 115792089237316195423570985008687907853269984665640564039457584007913129639936 raznih kombinacija tih 24 riječi. Ako pretpostavimo da imamo moć pogađanja 100 **triljuna** kombinacija _na sekundu_ (ni jedno moderno računalo nema), za isprobavanje svih kombinacija trebalo bi nam:

    115792089237316195423570985008687907853269984665640564039457584007913129639936 / 100000000000000 = 1157920892373161954235709850086879078532699846656405640394575840 sekundi
    
To je otprilike 36717430000000000000536992568032848736216424136408984408 godina. I to samo ako imate računalo moćnije od bilo čega što je čovječanstvu do sada palo na pamet.

Uzmimo za primjer drugi ekstrem - što ako znate nečijih 24 riječi, ali ne znate redoslijed? Broj mogućih kombinacija je 24! (24 faktorijela).

    24! = 620448401733239439360000
    
S jednako moćnim računalom trebalo bi nam:

    620448401733239439360000 / 100000000000000 = 6204484017 sekundi
    
 6204484017 sekundi je 196.6 godina.
 
 Dakle ako znate **sve** riječi u nečijoj kombinaciji ali samo trebate pogoditi redoslijed, treba vam 200 godina s računalom koje je danas nezamislivo. Ako ne znate riječi koje trebate pogoditi, broj se povećava 2048 puta za svaku koju ne znate - dakle ako ne znate samo jednu od njih, treba vam oko 400000 godina.

## Zaključak

Ledger je izuzetno siguran način spremanja vaših valuta koji daleko nadilazi obično spremanje privatnog ključa na USB stick. 

Ledger ima svoj procesor koji izračunava ključeve, što znači da vaš privatni ključ nikada ne dotiče računalo na kojem se koristi, i time nema rizika od curenja privatnog ključa na internet ni krađe sredstava. Osim toga, Ledger zahtjeva dodatnu potvrdu kod bilo koje transakcije pritiskom gumba na uređaju, te je time siguran od virusa i sve češćih sličnih metoda za krađu putem auto-transakcija. 

Ako se Ledger izgubi ili uništi, sva sredstva trivijalno je regenerirati ponovnim ukucavanjem početnih 24 riječi, no njih nije pametno izgubiti - držite ih na sigurnom, po mogućnosti u vatro-otpornim spremnicima ili u kopijama na više lokacija.

Na našoj stranici možete kupiti [Bitfalls-brendirani Ledger][ledger] po cijeni nižoj od [maloprodajne](https://ledgerwallet.com/products/ledger-nano-s). Moguće je kupiti i Ledger s dodatnim opcijama, poput Skype sata konzultiranja za početnike u kojem ćemo vam objasniti sve o tome kako Ledger funckionira i kako ga najbolje podesiti.

Za sva pitanja, stojimo vam na raspolaganju i [putem e-maila][mail]!

[ledger]: https://bitfalls.com/hr/product/ledger-nano-s-bitfalls/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[startbtc]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/
[mew]: https://myetherwallet.com
[mail]: mailto:contact@bitfalls.com