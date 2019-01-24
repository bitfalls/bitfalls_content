U [prošlom članku](https://bitfalls.com/hr/2019/01/18/make-your-crypto-work-for-you-how-to-create-dai/) naučili smo kako generirati DAI stablecoin koristeći ether. To je korisno kada želimo špekulirati ili upravljati likvidnošću našeg etera bez da ga zapravo prodamo.

U ovom ćemo članku naučiti kako koristiti [Compound Finance](https://compound.finance) platformu za posuđivanje DAIa i zarađivanje na kamatama - automatski i sigurno.

## Složena Kamata (Compound Interest)

Financijski termin _složena kamata_ je vrsta kamate koja raste na do tada skupljenoj kamati. Kao banalni primjer možemo navesti sljedeće. Zamislite da imate 1000 USD koje investirate na 10% za godinu dana. Nakon godine dana imate 1100 USD.

Složena kamata dolazi u igru kada se puni iznos ponovno investira jer ne izvlačite dobivenih 100 USD. Na taj način godinu dana kasnije imamo 1210 USD - dobili smo još 10 USD jer smo _složili_ kamatu.

10 USD ne zvuči kao ozbiljna količina novca, no kada se ova taktika primijeni na veće iznose i na dulje periode, [stvaraju se carstva](https://www.marketwatch.com/story/this-warren-buffett-rule-can-work-wonders-on-your-portfolio-2016-04-26).

Na primjer, $100,000 investirano na 5% godišnje daje $62000 nakon 10 godina. Nije baš neka sreća. No ako pustimo taj novac da sjedi do mirovine - 40 godina - imamo $600,000. Samo 10 godina više, i iznos se penje preko milijuna USD.

Dobra je ideja staviti ozbiljni dio svake plaće u račun s složenom kamatom kako bi taj iznos kontinuirano rastao. Tako se dolazi do daleko pouzdanije mirovine nego one koju nam obećaje država jer raste ne samo kamata nego i temeljni kapital.

![Warren Buffet](https://bitfalls.com/wp-content/uploads/2019/01/01.png)

## Compound Finance

Compound Finance je skup pametnih ugovora i korisničkog sučelja za korištenje istih. Ti ugovori omogućuju korisnicima da posuđuju kriptovalute i na tom posuđivanju - ovisno s koje su strane dogovora - plaćaju ili zarađuju kamatu.

Kao i MakerDAO CDP, Compound Finance omogućava polog u jednoj kriptovaluti za zajam u drugoj. Razlika je u tome da se kod Compound Finance posuđena kriptovaluta ne _generira_, već se posuđuje iz zajedničkog skupa. Čim je taj skup manji, veća je kamata koju neki ponuđač može dobiti kada daje kriptovalutu u zajam.

Pogledajmo na primjeru kako točno dati svoj DAI na zajam drugima.

### Kako posuditi DAI

Pretpostaviti ćemo da ste pratili [prošli članak](https://bitfalls.com/hr/2019/01/18/make-your-crypto-work-for-you-how-to-create-dai) te da imate nešto DAIa i Ethera na računu koji mislite koristiti. [MetaMask](https://bitfalls.com/hr/2018/02/16/metamask-send-receive-ether/) je za svrhe ovog primjera sasvim dovoljan za interakciju sa sučeljem.

Posjetimo sada [Compound finance aplikaciju](https://app.compound.finance).

Prvi ekran ispisuje vaše opće stanje računa - koliko ste posudili, ulazno, izlazno i dostupno za izvlačenje ili posudbu. Na istom ekranu su ti isti podaci raspoređeni po pojedinim podržanim kriptovalutama. U ovom smo primjeru kod svega na nuli.

![Compound Finance App](https://bitfalls.com/wp-content/uploads/2019/01/02.png)

Najbolja kamata je na DAI. Kliknite na taj red u tablici.

Kao i u prošlom članku o CDPovima, moramo dopustiti pametnom ugovoru da upravlja našim valutama klikom na Enable DAI. Ta se transakcija mora izvršiti samo jednom.

![Enable DAI](https://bitfalls.com/wp-content/uploads/2019/01/03-1.png)

Jednom kada aktiviramo DAI, omogućava nam se da kliknemo na Supply i ponudimo nešto našeg DAIa na posuđivanje.

![Supply DAI](https://bitfalls.com/wp-content/uploads/2019/01/04-1.png)

Ovo sučelje nam dopušta da DAI ubacimo u zajednički skup iz kojeg drugi tada posuđuju uz kamatu koju svi ponuđači tada dijele.

### Kamata

Uz jedva 3% kamate, manji iznosi nemaju puno smisla. Trebamo uzeti u obzir i 0.5% godišnju kamatu posuđivanja DAIa iz MakerDAO CDPa, pa nam efektivna kamatna stopa pada na 2.5%.

Bitno je imati i broj transakcija na umu. Kod malih iznosa (ulog od $5000 i manje), kamata je toliko mala da jedna transakcija može obrisati napredak cijelog dana. Ostavljanje novca u ovom sustavu isplati se jedno ako ga možemo ignorirati na dulje vrijeme.

Kamata se kontinuirano ažurira ovisno o ponudi i potražnji. Automatski se primjenjuje na kapital dinamički prilikom svakog novog ethereum bloka - cca svakih 15 sekundi. To znači da ulog raste za `(KAMATA/BLOKOVA_U_GODINI)` svakih 15 sekundi.

Sve je to vidljivo uživo u stvarnom vremenu. Vaš temeljni kapital, kamata i transakcijska povijest vidljivi su u sučelju. Kako mikorcenti počnu stizati, ukupan iznos zaslužene kamate i zbroj kamate i kapitala ažuriraju se dinamički.

Kao što je to vidljivo u primjeru dolje, kamatna zarada resetirala se na 0 kada je nadoplaćen ukupni iznos uloga na 5868 DAI 16. siječnja. Od tada je taj ulog zaradio 3.19 DAI. Zanemariv profit, što ponovno ukazuje na važnost složene kamate. Ako ulog ostavimo u sustavu na dulje vrijeme i samo povremeno mu manualno nadoplatimo još ponešto iznosa (10-50% plaće), dugoročno naš će povrat biti neusporedivo veći.

![Demo loan](https://bitfalls.com/wp-content/uploads/2019/01/05-1.png)

Kada ste spremni prestati posuđivati, jednostavno izvucite sav DAI na Withdraw opciji. DAI će se odmah prebaciti u vaš novčanik.

### Alternativna sučelja

Nabolje svojstvo ovog sustava je decentralizacija - sve je u pametnim ugovorima, što znači da svatko može izgraditi svoje vlastito sučelje za iste i da ih se može nastaviti koristiti i ako sučelje za Compound Finance nestane. Neka alternativna sučelja koja su već razvijena:

- [Bloqboard](https://app.bloqboard.com) spaja Compound i Dharma protokol u jednostavno i čitko sučelje za oba sustava posuđivanja na Ethereumu. Uz zajedničko posuđivanje iz Compound protokola, Bloqboard nudi i Dharma integraciju koja dopušta _peer-to-peer_ posuđivanje kako bi se posuđivalo izravno od osobe do osobe umjesto kolektivno. Budući da u tom slučaju blockchain služi kao posrednik, obje strane mogu biti sigurne u poštenje one druge.
- [MultiSupply](https://multi.supply) je alternativno sučelje za Compound Finance s više informacija (očekivana zarada nakon godinu dana).
- [Curious Giraffe](https://www.curiousgiraffe.io/compound/) je sučelje za čitanje analitičkih podataka o trenutnom stanju Compounda (i nekih drugih projekata). Sadrži mnogo korisnih i zanimljivih detalja.

Budite pažljivi prilikom korištenja sučelja koja su razvili drugi korisnici - pazite na dozvole koje im dajete i koliku proviziju naplaćuju, ako je ima. Neki će malo ostrugati zaradu s vrha vaše kamate, drugi će krasti transakcije koje prelaze neku veću količinu novca. Ove tri navedene u tekstu iznad su OK, no ukoliko nabasate na neku koja je iole sumnjiva, raspitajte se prije nego je počnete koristiti.

### Bonus: Kako nekoga likvidirati

Što se dešava kada netko posudi novac i vrijednost duga pređe likvidacijski omjer od 150% prema pologu? Likvidira ih se. Evo kako.

Ako odemo na [Conlanov Compound Likvidator](https://conlan.github.io/compound-liquidator) vidjeti ćemo postojeće dugove poredane po omjeru. Sve ispod 150% može se likvidirati. Čim manji omjer, tim veća moguća likvidacija.

_Prisjetimo se, likvidacija je plaćanje nečijeg zajma umjesto njih i dobivanje njihovog pologa u istom omjeru zauzvrat, uz popust._

Pogledajmo treći zajam u ovom popisu.

![Loan](https://bitfalls.com/wp-content/uploads/2019/01/06.jpg)

143% je jedva ispod omjera, no biti će dovoljno za naš primjer. Klik na zajam pokazati će više detalja.

![Loan details](https://bitfalls.com/wp-content/uploads/2019/01/07.jpg)

Zelene kvačice označavaju valute kojima pametni ugovor za likvidaciju smije upravljati preko našeg računa. Bitno je aktivirati one koje mislimo koristiti u ovom procesu - za mene su to bile REP i DAI jer namjeravam otplatiti REP i uzeti DAI za uzvrat.

_Napomena: aktivacija pojedinih valuta mora se učiniti samo jednom ukupno, ne na svakom zajmu kojeg likvidiramo._

Nabavio sam nešto REP-a kroz platformu [Coinvendor.io](https://coinvendor.io) i poslao je na svoj MetaMask novčanik. Proces za otplatu je sljedeći:

- odaberem kolateriziranu valutu koju želimo za isplatu nakon likvidacije (DAI)
- odaberemo pozajmljenu valutu koju želimo vratiti umjesto dužnika (REP)
- pomaknemo slajder na dnu do kraja desno za puni iznos otplate kako bismo odnos kolateralizacije doveli opet na 150%
- kliknmo Repay nakon što se uvjerimo da nam se procijenjeni povrat isplati (Estimated Return)

Nakon što se transakcija izvrši možemo pogledati što se sve odvilo:

![Transaction details](https://bitfalls.com/wp-content/uploads/2019/01/08.jpg)

Vidljivo je da:

- smo platili 0.0776 REP
- smo dobili 0.997634 DAI

Tada je cijena REP bila $12.24 što znači da bismo na otvorenom tržištu za 0.0776 REP dobili 0.949824 DAI, ili otprilike 5% manje nego ovdje. Da smo požurili na tržište i kupili REP u istom iznosu, završili bismo s malim profitom.

Naravno, s obzirom na transakcijske troškove i vrijeme potrebno da se ove akcije izvrše, ovi su iznosi potpuno beznačajni. No uglavnom se ni ne izvršavaju manualno - većinom su to botovi i skripte koji automatski promatraju stanje raznih zajmova i likvidiraju kada procijene da će troškovi gasa biti manji od dobitka. Ti isti botovi tada kupuju vraćena sredstva nazad na DEXovima (decentraliziranim burzama) i ostvaruju automatski profit koji, kao i kod složene kamate, postaje primjetan tek nakon dugo vremena.

Zbog toga ćete rijetko vidjeti _Unsafe_ zajmove na sučeljima poput ovog - veće se iznose isplati likvidirati pa brzo nestaju, a u sustavu ostaju samo _spam_ zajmovi i oni eksperimentalni koji uvijek koštaju više da ih se likvidira nego mogu donijeti profita.

Je li zbog toga loviti likvidacije borba s vjetrenjačama?

Da i ne - ovisi. Možda vam se posreći u momentu nenadanog pada tržišta, možda upogonite bota koji je brži od svačijeg drugog. Sve ovisi o vašoj ideji i implementaciji. Jedno je sigurno - incentivizacija lova na nepovoljne zajmove održava sustav na životu i čini ga poštenim do daljnjega. Tako dugo dok se može zaraditi na "cinkanju", sustav će ostati zdrav i balansiran.

## Zaključak

Kamata koju možete zaraditi na Compound Finance zaista nije ni blizu [moći dugoročnih dividendi dionica](https://www.suredividend.com/snowball-effect/), no ovo je blockchain - glavna prednost je sloboda. Sloboda od regulatora, poreznika, posrednika, sloboda od drugih koji vam zapovijedaju u što smijete a u što ne smijete uložiti vlastiti novac.

Pa što čekate? Napustite njihov sustav. Oslobodite svoje financije.