_Wallet_ ili _novčanik_ je posebna _adresa_ koja  može primati [kriptovalute][cc]. Možete je usporediti s email adresom. Svaki [blockchain][blockchain] ima svoju vrstu walleta, i trenutno ih većina nije međusobno kompatibilna (npr. nije moguće poslati Bitcoin na Ethereum adresu).

Svatko može imati koliko god adresa poželi, i ne postoji način da se adresa poveže s pravim identitetom korisnika, osim ako korisnik sam ne učini neke propuste ili to javno objavi. Na većini blockchainova stanje svačije adrese je javno - svatko vidi koliko koja adresa ima sredstava. Ako gledamo na to kao na email, wallet u kripto svijetu je kao email inbox kojeg svatko može pročitati, ali samo vlasnik može pisati odgovore. 

Način na koji se sredstva na nekoj adresi koriste je da se pomoću _privatnog ključa_ (kombinacije brojki i slova koju je matematički nemoguće pogoditi) potpiše izjava (tzv. transakcija) da se vrši prijenos sredstava s adrese A na adresu B, i to se onda šalje u blockchain na potvrdu od strane svih drugih korisnika. Naime, sredstva se u kriptovalutama ne miču doslovno, nego se vlasnikom neke valute smatra ona adresa koja je bila zadnja objavljena u blockchainu kao vlasnik te količine te valute. 

To je kao da osoba A ima prazne džepove, no 200 drugih oko nje jasno i glasno tvrdi da ona ima 500kn i svi to vjeruju bez dvojbe. Ako ta osoba kaže pred svih 200 svjedoka da daje osobi B svih 500kn, svi svjedoci će to potvrditi svakoj novoj osobi koja uđe u krug tih ljudi, pa će tako svaka pridošlica isto biti svjesna toga da osoba B sada vrijedi 500kn. Ako neki svjedok kaže suprotno, ostali će ga čuti i ispraviti - tako funkcionira [blockchain][blockchain].

Transakcije, tj. te potvrde prijenosa vrijednosti, potpisuju se privatnim ključem kojeg ima samo vlasnik adrese. Da biste dobili vlastiti novčanik (dakle javnu adresu + privatni ključ), postoji više načina:

- generirajte svoj ključ i adresu uz pomoć _klijenta_ (program blockchaina čija valuta vas interesira - kod Bitcoina to je npr. Electrum, kod Ethereuma to je npr. Mist, itd.)
- koristite neko hardversko rješenje poput [Ledger Nano S][ledger] - uređaja nalik USB sticku koji sprema vaš privatni ključ za vas i može sadržavati više adresa za više raznih valuta
- otvorite račun na nekoj kripto-mjenjačnici

Otvaranje računa na mjenjačnici je daleko najjednostavnije, ali jer mjenjačnice čuvaju vaš privatni ključ za vas, bilo kakvo dugotrajno držanje sredstava na takvim servisima je opasno. Neka mjenjačnica može bilo kojeg momenta nestati ili biti hakirana i vaša sredstva biti će izgubljena, kao što je to bilo s Mt. Gox i Bitfinex servisom. Ako i imate neki račun na mjenjačnici, preporučljivo je nakon što ste gotovi s mijenjanjem prebaciti sredstva na adresu koja je u potpunosti pod vašom kontrolom.

Kako do svoje prve adrese za željenu kriptovalutu, te kako primati i slati kriptovalute pročitajte [ovdje][wallet].

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[ledger]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[wallet]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/
