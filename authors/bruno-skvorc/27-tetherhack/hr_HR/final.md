Tether.to, tvrtka koja već neko vrijeme ima [sumnjive obrasce ponašanja][fraud] u kripto svijetu, [danas je objavila][announced] da je hakirana za 31 miljun USDTa. Prisjetimo se, Tether je tvrtka koja centralizirano izdaje digitalnu valutu "USDT" za koju tvrdi da je _tetherana_ (spojena) za USD u omjeru 1:1. Ta tvrdnja drži vodu ako pogledamo cijenu Tethera kroz vrijeme, koja varira minimalno.

![Tether cijena kroz vrijeme](https://bitfalls.com/wp-content/uploads/2017/11/01-3.png)

Zanimljivo je to da je ukraden USDT, a ne neka druga valuta, što je čudno s obzirom da su Tetheri zapravo [bezvrijedni][tether1]. Tetheri zapravo nisu [kriptovaluta][cc], već su samo token na [Omni] sloju, što nije [blockchain][bc] samo po sebi, već softverska implementacija izgrađena na Bitcoin mreži - sloj s dodatnim mogućnostima koji koristi Bitcoin transakcije _pod haubom_.

Sumnjiv je i način na koji se ovaj problem "rješava". Naime, iz Tethera su odlučili napraviti nenajavljenu izmjenu koda [Tether novčanika][wallet] - tzv. hard fork - koji čini sve trenutne implementacije novčanika koji nisu na toj verziji nekompatibilnima. Specifično, u samom kodu novčanika blokirali su jednu specifičnu adresu i to na takav način da sredstva mogu samo stići na istu, a ne biti i poslana s nje, efektivno zarobivši ukraden USDT na jednom mjestu.

![Tetherova solucija](https://bitfalls.com/wp-content/uploads/2017/11/02.jpg)

Ono što je problematično oko ovoga je sljedeće:

- Tether pokazuje koliko je USDT centraliziran kao kriptovaluta. Sve odluke su u njihovim rukama, kao i proizvodnja novih USDT.
- Tether pokazuje kako ima potpunu vlast nad softverom koji se koristi za primanje i slanje USDTa - činjenica da su tu izmjenu u kodu napravili tako brzo i počeli nagovarati razne burze da odmah ažuriraju svoje programe ima sve znakove centralizirane korporacije / tvrtke.
- Tetherova sposobnost da ovako direktno upravlja mogućnošću prijenosa sredstava s jedne adrese na drugu je zabrinjavajuća, i otvara vektor napada za državne i nadzorne institucije koje žele istome stati na kraj.

## Kamo dalje?

Jedini način da se Tether osigura i postane vjerodostojna tvrtka je da doda sloj regulacije, kao što smo pojasnili [ovdje][dkuna]. Nažalost, ne postoji nikakva šansa da će se to ikada desiti - Tether u ovom stadiju nikad ne bi dopustio potpunu reviziju ili nadzor. Što, stoga, možemo očekivati u budućnosti? Gdje saznati još informacija?

Budući da na sumnjive radnje Bitfinex / Tether tvrtki upozoravamo već neko vrijeme, kako [u člancima][fraud] tako i [na konferencijama][f2], ovakvi nas propusti ne iznenađuju i očekujemo samo još gori razvoj situacije. Ako želite saznati više o svim aspektima ove sumnjive kolaboracije, pogledajte sljedeći jučerašnji razgovor Tone Vaysa, Jimmy Songa, Bitfinexeda, Flibbera, i BTCVIX-a u kojem se otkriva koliko zapravo vjerodostojnosti Bitfinex ima kao burza, i koliko je realno da se približavamo još jednom MtGox scenariju (MtGox je bila najveća Bitcoin burza s koje je misteriozno nestalo 800,000 BTCa).

<iframe width="560" height="315" src="https://www.youtube.com/embed/TerIjELO7IY" frameborder="0" allowfullscreen></iframe>

Da biste se uspješno obranili od novih MtGox scenarija i sačuvali svoja sredstva, bitno je ne držati ih na mjenjačnicama i burzama, nego u privatnom novčaniku i [dobro ga osigurati][secure].

Trgujte pažljivo!

[dkuna]: https://bitfalls.com/hr/2017/10/31/dkuna-use-case-government-cryptocurrency-option/
[f2]: http://f2.bug.hr
[tether1]: https://bitfalls.com/hr/2017/10/21/the-curious-tale-of-tethers/
[fraud]: https://bitfalls.com/hr/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[omni]: http://www.omnilayer.org/
[secure]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[announced]: https://tether.to/tether-critical-announcement/