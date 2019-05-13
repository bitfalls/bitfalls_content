# Ne Prati Web3 - Koliko je vaš mobilni kripto novčanik privatan?

Istražujući neke [blockchain](https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/) novčanike s podrškom za više identiteta tj. računa za [Wallets.Review](https://wallets.review), primijetio sam da ne znam što pojedine aplikacije rade s mojim kripto identitetima, te povezuje li ih netko i prodaje te podatke bez da ja to znam.

Dva su moguća problema.

## Aplikacija je maliciozna

Prvi problem se javlja kad je novčanik zatvorenog kôda. Kada nemate mogućnost da provjerite izvorni kôd aplikacije, moguće je da aplikacija šalje nekom serveru podatke o svakoj adresi koja se kroz istu koristi. Tada je lako povezati razne identitete u jedan i [takvi se osobni podaci brzo prodaju](https://haveibeensold.app).

Ovaj se problem može riješiti na dva načina.

### Koristite samo novčanike otvorenog kôda.

Kada je kôd nekog novčanika otvoren, lako ga je pregledati i razumjeti što radi s vašim podacima, kako, i kada. Možda ga vi sami ne možete pročitati no netko drugi  može pa budite sigurni da je aplikacija pod budnim okom mnogih entuzijasta.

Ono što je najbitnije kod novčanika otvorenog kôda je da ih počnete koristiti tek nakon što aplikacija već ima kritičnu masu korisnika. One koji dolaze ranije koristite kao ljudski štit - neka isprobaju sigurnost prije vas.

![Operation human shield](https://bitfalls.com/wp-content/uploads/2018/10/humanshield.jpg)

### Koristite samo revidirane aplikacije.

Ako neka aplikacija ne želi objaviti svoj izvorni kôd zbog sigurnosnih ili poslovnih razloga, trebali bi barem objaviti revizije svog softvera od strane nekih [reputabilnih revizorskih kuća](https://audithor.io). Revizija će nam reći dvije stvari.

Prvo, reći će nam da su autori aplikacije u tom poslu s dugoročnim namjerama. Ne samo da su našli financije za reviziju (revizije su obično veoma skupe), već su i investirali vremena u svoj kôd da ga ispoliraju, pripreme za pregled, i da počekaju završetak revizije. To nam govori da im se ne žuri, što je veoma bitna osobina u kripto svijetu.

Drugo, ako je tvrtka koja radi reviziju reputabilna ili ljudi koji je predstavljaju imaju dovoljno velik ulog za izgubiti laganjem ili lošom procjenom, implicitno se može više vjerovati rezultatima revizije jer je gubitak potencijalnog posla mnogo veći od moguće zarade podržavanjem maliciozne aplikacije.

Naravno, sveti gral je naći aplikaciju koja je i otvorenog kôda, i revidirana.

Treba napomenuti da ukoliko se radi o aplikaciji zatvorenog kôda vjerojatno imate bitnije stvari o kojima brinuti - primjerice, jesu li [vaši privatni ključevi zapravo vaši](https://wallets.review/attributes.html#keys) ili se i oni šalju na neki server pod nečijom kontrolom gdje se skupljaju ključevi svih korisnika sve dok se ne skupi dovoljno novca na raznim računima da se kolektivno financira bijeg.

## Dapp je maliciozan

Ovaj problem je aktualan samo ako aplikacija dolazi s dapp preglednikom (web3 preglednikom). Dappovi su decentralizirane aplikacije, tj. aplikacije s web3 mogućnostima.

Kada koriste dapp preglednik, mnogi korisnici nemaju svoj kripto identitet na umu. Situacija je donekle poboljšana na desktop preglednicima MetaMaskovom odlukom da [više ne pokazuje svim web stranicama vašu Ethereum adresu](https://thenextweb.com/hardfork/2019/03/22/metamask-ethereum-privacy-address/), no na mobitelu je teško procijeniti što se događa čak i nakon što ste aplikaciji dopustili da vidi i koristi vašu adresu. Važi li to samo taj jedan put? Za samo tu adresu ili za sve? Samo u tom pregledniku ili na cijelom uređaju?

Pogledao sam više novčanika za [Wallets.Review](https://wallets.review), no kao što možete zamisliti, temeljito testiranje aplikacija - pogotovo kripto novčanika - iziskuje mnogo vremena. Stoga ih je trenutno samo 9 na stranici, a njih 6 imaju dapp preglednik: Status, Trust Wallet, AlphaWallet, imToken, Coinbase Wallet i Opera. Od tih 6, samo [Status](https://wallets.review/apps/status) je imun na ovaj vektor napada.

Pa o kakvom se točno napadu radi?

Dapp sam odlučuje što će učiniti s vašom adresom i prije i poslije mijenjanja kripto identiteta u aplikaciji: može zapisati adrese u kolačić ili localstorage (u daljnjem tekstu kolačić za oboje), i kada ih skupi dovoljno (dvije ili više), spremiti na serveru gdje povezuje identitete i prodaje te informacije. Sama aplikacija ima vrlo malo kontrole nad tim procesom, i moj je prijedlog da svaka aplikacija koristi tu kontrolu do maksimuma.

Naravno, dapp može pratiti adrese i tako da bilježi User Agent vrijednost preglednika same aplikacije i IP adrese i prema tome prepoznaje identičnog korisnika više Ethereum adresa, no to nije moguće ako preglednik odabere koristiti neki općeniti UA da bi se maskirao (a svi preglednici bi trebali to raditi!). Nažalost, budući da većina mobilnih kripto novčanika s podrškom za dappove jednostavno koriste ono s čime njihov softver dolazi bez da imalo modificiraju stvar, rijetko koji tim odluči [podesiti UA na nešto drugo](https://stackoverflow.com/questions/36590207/set-user-agent-with-webview-with-react-native).

Evo kako provjeriti jeste li sigurni protiv ove vrste curenja privatnih informacija.

Razvili smo mali alat - jednostavnu web3 stranicu koja će zapisati svaku Ethereum adresu s kojom je posjetite, i ispisati je na ekranu prilikom osvježavanja stranice. Možete je koristiti da provjerite briše li vaš dapp preglednik kolačiće između posjeta i/ili između mijenjanja kripto identiteta. Na stranici je i gumb za lako čišćenje kolačića radi ponovnog testiranja.

Alat je [Don't Track Web3](https://wallets.review/dont-track-web3.html).

![Don't Track Web3](https://bitfalls.com/wp-content/uploads/2018/10/dont-track.png)

Isprobajte ga i [javite mi](https://twitter.com/bitfalls) što vaš dapp novčanik kaže da ga mogu dodati na stranicu! Ako znate neke programere koji rade na novčanicima, recite im da isprobaju privatnost svojih uradaka na ovom alatu!

## Zaključak

Budite konzervativni s povjerenjem prema aplikacijama u ovom novom svijetu kripto ekonomije. Neka vas ne zavaraju dobra korisnička sučelja ili bogatstvo mogućnosti - ako je aplikacija besplatna, vjerojatno je plaćate nekako drugačije. Uvijek odaberite aplikacije otvorenog kôda ili one koje su temeljito revidirane.

Nikada nemojte na mobilnim novčanicima držati više novca nego biste imali u džepu. Dok mnoge aplikacije danas nude razne prednosti i mogućnosti za osobne financije od ulaganja do posuđivanja kriptovaluta, držati velike iznose u dometu otiska prsta nije najpametnija ideja iz očitih razloga.

Iako možda ne smatrate svoju imovinu pretjerano vrijednom u ovom momentu, vjerujte mi da ste upravo Vi uvijek _nekome_ vrijedni. U najmanju ruku kao varijabla u procesu [identificiranja nekoga drugoga](https://audithor.io/digital-forensics/), a u najgorem slučaju ste noćna mora vas samih iz budućnosti kada na vrata pokuca kripto-porezna.