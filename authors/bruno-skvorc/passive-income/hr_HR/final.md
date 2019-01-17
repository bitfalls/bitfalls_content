Decentralizirane Financije (DeFi) su novo područje razvoja u [blockchain](https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/) sferi. Prioritet je na uspješnom odstranjenju banaka, regulatora i posrednika iz financijske industrije te omogućavanju krajnjim korisnicima da preuzmu vlastite financije u vlastite ruke.

U ovom ćemo članku pogledati sustav zajmova i stablecoinova preko MakerDAO projekta. U sljedećem ćemo članku naučiti kako natjerati naš novac da _radi za nas_.

## MakerDAO i CDP

CDP je _collateralized debt position_ ili kolaterizirani zajam. Laički, to znači da možete uzeti zajam za polog (kolateral) u kriptovalutama koje posjedujete. Taj polog garantira da ćete vratiti zajam, a ako taj dogovor prekršite, vaš polog će biti automatski likvidiran da se pokrije dug. Smatrajte CDPove hipotekama na [kriptovalute](https://bitfalls.com/hr/2017/08/20/cryptocurrency/).

### DAI i MKR

[MakerDAO](https://makerdao.com) je organizacija koja je iza DAI stabilnog coina. DAI (koji ima odnos 1:1 s USD) za razliku od drugih _stablecoinova_ nema odgovarajući fiat polog u nekoj banci, već je u cijelosti generiran isključivo iz pologa [ethera](https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/) u MakerDAO CDP sustavu pametnih ugovora. Ti pametni ugovori tada dopuštaju zajmove u DAIu, a kako DAI vraćate (s kamatom od 0.5% godišnje), vraća vam se vaš polog. Polog se likvidira ukoliko cijena ethera previše padne, no ukoliko se počnete približavati granici likvidacije lako je platiti dio duga ili dodati još ethera u CDP kako biste omjer pomakli u svoju korist (primjer toga vidjeti ćemo u tekstu malo niže). Cijenu ethera sustavu javlja grupa _oraclea_, tj. vanjskih servisa koje pokreću strane kojima MakerDAO vjeruje, i čiji su identiteti poznati isključivo MakerDAO Oracle timu. To je ujedno najcentraliziraniji i najosjetljiviji dio MakerDAO konstrukcije.

Osim toga, MakerDAO ima i MKR token koji ima ulogu "vlasničkih dionica" u MakerDAO sustavu. Taj token se koristi za dodatnu likvidnost u slučaju da svi polozi postanu nedovoljni da se pokriju svi dugovi - npr. kod velikog kraha tržišta. Do sada to nije bilo potrebno, čak ni kod prošlogodišnjeg pada ethera od 94%, što DAI čini najstabilnijim stablecoinom na tržištu.

### Svrha MakerDAO sustava

Ukratko, cijeli je taj sustav osmišljen da vam omogući sljedeće:

1. Kreiranje zajma u DAI (dolarima) baziranog na količini vaših kriptovaluta
2. Korištenje DAIa na bilo koji način koji vam odgovara
3. Vraćanje DAIa kada poželite izvaditi svoj polog

Ako vrijednost ethera naraste, vratite DAI i imate vrijedniji ether. Još bolje - ako vrijednost ethera naraste, iskoristite pogodniji omjer kolateralizacije za kreiranje još DAIa i povećanje svoje likvidnosti, jer veći raspon između tretnutne vrijednosti ethera i vrijednosti ethera kojom je generiran DAI znači pogodniji omjer za vas. Ako pak vrijednost ethera počne padati, lako vratite DAI i izvadite polog prije likvidacije sve dok vam omjer ostaje iznad 150%.

Na primjer:

Ako ste koristili 1 ether da generirate 60 DAI po cijeni od 120 USD po etheru, vaš omjer kolateralizacije je 200% (120/60). Ako cijena ethera padne na 90 USD, vaš je polog riskantan i može ga se likvidirati čim ode ispod 150%. Onaj tko pokrene likvidaciju (to može biti bilo koji promatrač) dobiva malu nagradu u postotku vašeg pologa, a ostatak se likvidira za pokrivanje minusa, penalizira s dodatnih 13%, i sve što ostaje vraća vam se.

Probajmo kreirati nešto DAIa da objasnimo stvar na primjeru.

### Kreiranje DAIa

MakerDAOv CDP proces podržava [MetaMask](https://bitfalls.com/hr/2018/02/16/metamask-send-receive-ether/), [Ledger](https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/) i Trezor. Posjetite [cdp.makerdao.com](https://cdp.makerdao.com).

![CDP home page](../images/01.png)

Korsitit ćemo MetaMask. Otključajte vaš [kripto novčanik](https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/) koji ima nešto ethera i pokazati će vam se sljedeći ekran:

![No CDP open](../images/02.png)

Ovaj će ekran ispisati koliko točno koje podržane valute imate u otključanom novčaniku.

_Napomena: DAI i MKR su ERC20 tokeni, što znači da MakerDAO pametnom ugovoru treba dati dozvolu da njima upravlja s vašeg novčanika. Za to služi "Unlock" stupac. Otključavanje svake od tih valuta pokrenuti će posebnu transakciju i to je potrebno učiniti samo jednom. Budući da će vam to ionako biti potrebno kasnije ukoliko namjeravate koristiti ovaj sustav, najbolje je otključati obje odmah._

Otvorimo sada CDP s 0.9 ethera. **Nikada ne kolateralizirajte sav ether koji imate! Trebati će vam nešto ethera za troškove transakcija!** Kliknite na "Open CDP".

Sljedeći ekran omogućava unos iznosa DAIa koji želimo generirati i unos iznosa ethera kojim garantiramo da ćemo taj dug u DAIu vratiti. Ja ću odabrati siguran omjer od 217% - 50 DAI za 0.9 eth.

![Setting CDP parameters](../images/03.png)

Sljedeći ekran obavijestiti će vas da je otvaranje CDPa proces od 7 uzastopnih transakcija koje će radi praktičnosti biti automatizirane. Ukoliko vas interesira koje su to transakcije i što koja od njih radi, kliknite na strelicu kraj te obavijesti za proširenje ekrana i dodatne detalje. Potvrdite kreiranje CDPa i malo pričekajte dok se sve transakcije ne izvrše.

Čim su transakcije potvrđene na Ethereum blockchainu, njihova potvrda biti će vidljiva i na Etherscanu gdje možete proučiti detalje.

![Transaction inspection](../images/04.png)

Naš je CDP sada otvoren.

![CDP screen](../images/05.png)

Na ovom nam se ekranu nude 4 opcije.

- **Deposit** nam dopušta da "dopunimo" CDP s etherom, kako bismo pomakli omjer kolateralizacije u našu korist ukoliko nam prijeti likvidacija, ili kako bismo si omogućili da na siguran način kreiramo još DAIa.
- **Withdraw** nam omogućava da izvadimo neku količinu ethera iz CDPa, do 150% omjera kolateralizacije. Možete izvaditi i manje od toga, no bitno je imati na umu da svako vađenje smanjuje taj omjer pa treba biti pažljiv.
- **Payback** nam dozvoljava vraćanje duga - u cijelosti ili djelomično. To ima isti efekt kao i Deposit, samo što ovjde vraćamo DAI pa se omjer pomiče s te strane i dozvoljava nam da izvučemo više ethera.
- **Generate** nam dopušta da generiramo određenu količinu DAIa što smanjuje naš omjer kolateralizacije. To je posebno korisno kad etheru naraste cijena pa se omjer sam pomakne i time nam otvori prostora za generiranje još DAIa za istu količinu ethera a sve bez rizika.

DAI je sada već u našeom novčaniku, kao što to možemo vidjeti iz podataka na desnoj strani ekrana. Lako je taj podatak provjeriti i izravnom provjerom samog novčanika:

![Metamask has 50 DAI](../images/06.png)

Sada možemo koristiti DAI na burzama koje ga podržavaju, za špekulaciju s drugim kriptovalutama, [web kupnju](https://ava.do), itd.

_Napomena: u bliskoj budućnosti MakerDAO će omogućiti otvaranje CDPa i drugim kriptovalutama, ne samo etherom._

## Zatvaranje CDPa

Da bismo zatvorili CDP i vratili svoj polog, potrebno je vratiti puni iznos u DAIu. Kliknimo Payback i... opa! Što je sada ovo crveno upozorenje?

![CDP payback](../images/07.png)

MakerDAO sustav opstaje pomoći dodatne globalne kolateralizacije u MKR tokenima. MKR tokeni daju sustavu dodatnu likvidnost, a ujedno služe kao i "članarina" za korištenje MakerDAO pametnih ugovora. Zbog toga payback naplaćuje kamatu kod vraćanja duga (0.5% godišnje) u MKR tokenima ili u DAIu. No, ako plaćate u DAIu jer nemate MKR tokena, tada nije moguće vratiti sav iznos osim ako niste nabavili dodatnu količinu DAIa koja bi pokrila tu proviziju. To je noćna mora iz perspektive korisnika, i predložio bih MakerDAO timu da je čim prije adresira.

Srećom, ovaj je problem moguće zaobići u kritičnim momentima. Ako cijena ethera počne dramatično padati i vaš polog postaje rizičan sve bržim približavanjem omjeru od 150%, možete vratiti i samo dio DAIa i odabrati plaćanje provizije u DAIu. Time ćete si povećati omjer i smanjiti izloženost riziku. Pogledajmo kako izvršiti djelomični povrat zajma.

![Partial payback](../images/08.png)

![New ratio](../images/09.png)

Svakako vrlo privlačan omjer! Šanse za likvidaciju su dramatično umanjene jer je cijena ethera na kojoj dolazi do nesigurnog omjera od 150% sada postala 33 USD. Ako pogledamo naše stanje DAIa uočiti ćemo da nas je ova provizija koju smo platili u DAIu koštala _manje od sedam miljuntinki_ DAIa.

![DAI dust cost](../images/10.png)

Ovakve iznose zovemo DAI prašinom. Ipak, dovoljno da se uzrokuju problemi pa je dobro uvijek imati malo DAI ili MKR prašine na računu za pokrivanje provizije.

Nadoplatimo sada svoj račun s malo DAIa ili MKRa iz drugih izvora (decentralizirane burze popit Idex, OasisDex, Kyber itd su super i ne trebaju verifikaciju) da potpuno zatvorimo ovaj CDP. Koristiti ću DAI u primjeru da otplatim preostalih 20 DAIa.


![Close the CDP](../images/11.png)

![Empty CDP](../images/12.png)

Nekoliko transakcijskih potvrda kasnije naš CDP biti će prazan. Neće nestati, već će ostati kao "platforma" na kojoj dalje možemo koristiti MakerDAO sustav po volji. Da potpuno zatvorimo i obrišemo CDP povezan s ovom MetaMask ethereum adresom možemo kliknuti na Close CDP gumb gore desno. Tada nas aplikacija upozorava da moramo otplatiti sav DAI (što smo već učinili) te nakon potvrde briše CDP iz sustava pametnih ugovora.

![Pay back DAI](../images/13.png)

## Likvidacija

Što se događa kada omjer pologa i zajma padne ispod 150%?

Ako ste u ulozi dužnika, izloženi ste likvidaciji. 13% vašeg pologa uzima se kao kazna dok će ostatak biti prodan na slobodnom tržištu po popustu da bi se ubrzala likvidacija. Ako ste promatrač koji uoči neki rizični CDP možete pokrenuti proces likvidacije i ukoliko bude uspješan dio kazne dužnika pripisuje se vama kao nagrada. Time se potiče korisnike da drže tržište stabilnim i traže rizične CDPove - najlakše je to činiti [preko botova koji to rade za vas, automatizirano](https://developer.makerdao.com/keepers/), no opis korištenja istih je izvan konteksta ovog članka.

Za više informacija o likvidaciji [ovaj fantasitčni FAQ s Reddita](https://www.reddit.com/r/MakerDAO/comments/8efk5q/faq_possibly_everything_you_ever_wanted_to_know) je odličan izvor informacija.

---

U nastavku ćemo pogledati kako gore generirani DAI možemo iskoristiti za dobivanje kamata.