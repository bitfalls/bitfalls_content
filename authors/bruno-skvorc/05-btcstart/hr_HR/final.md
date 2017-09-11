## Generiranje adrese

Jedan od najjednostavnijih načina za generiranje adrese koja prima BTC je preko [BitAddress.org](https://www.bitaddress.org). 

Mičite mišem do kad brojač ne pokaže 100% ili sami unesite neku frazu ili nasumične brojke i slova - nije bitno, i ne morate ih pamtiti. Ovaj korak radimo kako bismo u generiranje adrese uveli element nasumičnosti.

Nakon što je brojač došao do 100%, vaša adresa biti će vidljiva na ekranu:

![Generirana adresa](https://bitfalls.com/wp-content/uploads/2017/09/01.png)

Zeleni dio (ovaj koji počinje s 195 na slici) je vaša adresa, i njeno stanje može se u bilo kojem momentu provjeriti [ovdje](https://blockexplorer.com/address/195sYZTRik2y3gidQZ3svoU7NexoLPJopr). Ta adresa je adresa koju unosite u polje primatelja kada na nju šaljete neki iznos Bitcoina.

Crveni dio - ovaj koji u našem slučaju počinje s L3SR - je privatni ključ koji služi za otključavanje te adrese i slanje BTCa s nje na druge adrese. To je dio koji morate držati na sigurnom mjestu. 

Najbolje je spremiti ga u tekstualnu datoteku, pa na USB i u ladicu/sef, ili prepisati na komad papira ili ugravirati u metalnu pločicu, pa to pospremiti na sigurno.

## Primanje BTCa

Da biste primili BTC na generiranu adresu, dovoljno je dati javni dio adrese (npr. ovaj koji počinje s 195 u gornjem primjeru) pošiljatelju. Pošiljatelj **nikada** ne treba vaš privatni ključ - ukoliko vas netko ikada zatraži za vaš privatni ključ za svrhe slanja sredstava na vašu adresu, pokušava vam ukrasti sredstva. Molimo vas da take incidente [prijavite][mail].

## Slanje BTCa

Ako imate BTC na računu neke mjenjačnice, nađite opciju "Send" ili "Withdraw". U _Recipient address_ polje unesite adresu na koju šaljete BTC, i to je to.

Da biste poslali BTC s generirane adrese koja je primila neka sredstva a čiji je privatni ključ u vašem vlasništvu, potreban vam je softver koji generira i potpisuje transakciju. Pritom će biti potrebno učitati privatni ključ u taj softver. Zbog toga, savjetuje se da se svaki wallet koji ikad učitate u bilo koji softver za slanje sredstava iskoristite u potpunosti i zaboravite - rizik da je privatni ključ sada prisutan na nekom drugom serveru je prevelik. Ukoliko s nekog walleta nekome šaljete samo dio sredstava, predlaže se da ostatak pošaljete na vlastitu, svježe izgeneriranu adresu.

Na stranici [Blockchain.info](https://blockchain.info) kreirajte korisnički račun. Kada stignete na svoj _Dashboard_ (početnu stranicu računa), kliknite na "Settings", pa na "Addresses".

<img src="https://bitfalls.com/wp-content/uploads/2017/09/02.png" alt="Addresses opcija" width="350">

Zatim, kliknite na "Import Bitcoin Address".

![Import Bitcoin Address opcija](https://bitfalls.com/wp-content/uploads/2017/09/03.png)

Sljedeći ekran ponuditi će vam da skenirate QR kod ili ručno unesete privatni ključ walleta s kojeg želite slati sredstva.

![Import Existing Bitcoin Address opcija](https://bitfalls.com/wp-content/uploads/2017/09/04.png)

Nakon unosa, sredstva će biti spremna za slanje. Tada možete kliknuti na "Send" pri vrhu ekrana, i poslati neku količinu na neku drugu adresu.

## Sweep? Import?

Bitno je razumijeti razliku _sweepa_ i _importa_.

Import, ili unošenje privatnog ključa u softverski wallet, omogućava originalnom vlasniku privatnog ključa (bio on vi ili netko drugi) da još uvijek koristi sredstva s tog walleta. Ako ste sigurni da ste samo vi ikada koristili taj wallet s tim privatnim ključem, import je sigurna metoda.

_Sweep_ je metoda pri kojoj se privatni ključ ne samo unosi u softverski wallet, nego se i sredstva _u potpunosti_ odmah šalju na novu adresu koju generira sam wallet. Time se osigurava da taj iskorišteni privatni ključ više ničemu ne služi jer njegovo unošenje u neki drugi wallet ne dopušta korištenje istih sredstava. Nedostatak sweepa je to da zahtjeva transakciju (prijenos na drugu adresu), te time zahtjeva plaćanje _mining fee_ (trošak rudarenja), koji varira iz dana u dan, i određeno vrijeme za potvrdu transakcije što, ovisno o zakrčenosti mreže, može potrajati satima.

Ako je ikad itko drugi koristio ili vidio privatni ključ koji mislite koristiti, ili vam je netko drugi dao isprintani novčanik (paper wallet), _sweep_ je sigurnija metoda, bez obzira na trošak.

## Alternative

Budući da će u slučaju prestanka rada Blockchain.info stranice gore navedena procedura prestati raditi, postoje sljedeće alternative:

- Blockchain.info mobilne aplikacije ([iOS](https://itunes.apple.com/us/app/blockchain-bitcoin-wallet/id493253309?mt=8) / [Android](https://play.google.com/store/apps/details?id=piuk.blockchain.android&hl=en))
- [Electrum](https://electrum.org/#home)
- [Mycelium](https://play.google.com/store/apps/details?id=com.mycelium.wallet&hl=en) Android aplikacija
- [Breadwallet](https://breadwallet.com/)
- [Bitcoin core](https://bitcoin.org/en/download)

[mail]: mailto:contact@bitfalls.com