Novčanik i [Ethereum][eth] program (klijent) Parity danas je [objavio](https://paritytech.io/blog/security-alert.html) kritični sigurnosni propust u svojoj implementaciji multi-sig adresa.

**Sredstva nisu izgubljena - samo se ne mogu micati iz Parity multi-sig računa - privremeno su zaključana**

Podsjetimo se, multi-sig adrese su "novčanici" kod kojih je potrebno više privatnih ključeva za autorizaciju transakcije, a ne samo jedan. Zadnji multi-sig propust dogodio se u [srpnju 2017.](https://paritytech.io/blog/security-alert-high-2.html) i ovaj je direktno uzrokovan kodom koji popravlja prošli. U prošlom propustu bilo je moguće preuzeti kontrolu nad multi-sig računom nekog drugog korisnika pozivanjem posebnog koda koji bi tu kontrolu prebacio. Ta je greška riješena, no izvorni kod samog tog rješenja ostao je dovoljno ranjiv i ujedno apstraktan da jedna promjena na istom uzrokuje grešku na svim multi-sig računima koji taj popravak koriste.

Upravo takav poziv dogodio se danas, i time su svi računi bazirani na tom popravku ostali zaključani i neupotrebljivi. Ponovno napominjemo - **sredstva su na sigurnom**, samo ih se ne da izvaditi iz tih računa. Kriptovalute su [uvijek spremljene na blockchainu][miscon], a ne na samom novčaniku ili uređaju koji se koristi.

Očekujemo daljnji razvoj situacije.

[miscon]: https://bitfalls.com/hr/2017/10/21/2-common-misconceptions-hardware-wallets/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/