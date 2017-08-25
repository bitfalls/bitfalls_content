Zbog decentralizirane prirode Bitcoina (vidi [blockchain][blockchain]) i ostalih [kriptovaluta][cryptocurrency], mnogi ih smatraju nezaustavljivima.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EQO1AUuFnyg" frameborder="0" allowfullscreen></iframe>

Naime, ako se radi o sustavu u kojem sudjeluju miljuni ljudi diljem svijeta, tada jednostavno nije moguće svima ugasiti računala istovremeno kako bi Bitcoin stao s radom, nije li tako?

Kao i s većinom odgovora na pitanja u vezi kriptovaluta, i ovaj je kompliciran.

## BitTorrent

Mnogi kriptovalute uspoređuju s torrentima, tj. prijenosom podataka putem [BitTorrent protokola](https://en.wikipedia.org/wiki/BitTorrent) - sustavom za razmjenu datoteka koji se danas, budimo iskreni, najviše koristi za skidanje piratskog materijala - TV serija i računalnih igara.

![Game of thrones pikselizirani](https://bitfalls.com/wp-content/uploads/2017/08/48730a251905d5e98382dddd88f37cc6.gif)

Radi se o sustavu u kojem netko tko ima određenu datoteku dopušta drugima da je preuzimaju od njega. Osoba koja tu datoteku preuzima zove se _leecher_ (pijavica) a ona koja je pruža zove se _seeder_ (sjeme). Više leecheva može preuzimati od više seedova, pa tako ako jedan seed nestane, datoteka ostaje dostupna tako dugo dok postoji barem jedan seed. Jedini način da se zaustavi širenje neke datoteke je da se ubiju svi njeni seedovi. Budući da ne postoji centralni autoritet na kojem su datoteke pohranjene (jer su na individualnim računalima korisnika torrent mreže), a torrent sustav je globalan, takva vrsta širenja podataka smatra se nezaustavljivom.

Kriptovalute funkcioniraju na sličan način, kao što smo već objasnili u članku o [blockchainu][blockchain].

No, dok se torrenti bave prvenstveno medijima (knjige, filmovi, serije, igre), kriptovalute bave se financijama - i tu stajemo na žulj nekome puno opasnijem od medijskih konglomerata: vladi.

## Kako Zaustaviti Bitcoin

Postoji više načina kako oslabiti i/ili ubiti Bitcoin i ostale kriptovalute.

### Packet Inspection

Prvi način je deep packet inspection, ili dubinsko pregledavanje podataka koji se šalju preko internetske mreže nekog pružatelja usluga. Detektirati korištenje Bitcoin (ili nekog drugog blockchain protokola) je trivijalno, i sve što država treba učiniti je blokirati takvu vrstu prometa. Svi korisnici koji nisu vješti u izbjegavanju takvih metoda (korištenjem Tor mreže ili raznih proxy servisa) automatski su izbačeni iz sustava. Slično se desilo u Turskoj kada je vlada, da bi spriječila promet prema socijalnim medijima, [blokirala Facebook, Twitter, i Whatsapp](http://www.telegraph.co.uk/technology/2016/12/20/turkey-blocks-access-facebook-twitter-whatsapp-following-ambassadors/).

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Confirmed: Social media slowdown for many users detected in <a href="https://twitter.com/hashtag/Turkey?src=hash">#Turkey</a> after <a href="https://twitter.com/hashtag/Russia?src=hash">#Russia</a> ambassador shooting broadcast ban<a href="https://t.co/Fga9p84TIq">https://t.co/Fga9p84TIq</a> <a href="https://t.co/V8jyjWW6mS">pic.twitter.com/V8jyjWW6mS</a></p>&mdash; Turkey Blocks (@TurkeyBlocks) <a href="https://twitter.com/TurkeyBlocks/status/810916025189486592">December 19, 2016</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Iako se to ne čini kao veliki problem jer većinski dio mreže ostaje na životu, jedan koordinirani napad na razini, primjerice, cijele Europe bio bi koban za prosječnog korisnika koji je tek ušao u kripto vode. Još gore, sve IP adrese svih korisnika Bitcoin protokola su javne, te je bez tih metoda skrivanja trivijalno naći pravi identitet i lokaciju korisnika, a kao što smo vidjeli gore u slučaju Turske, i Tor promet je lako blokirati. Više o *pravoj* anonimnosti u svijetu kriptovaluta saznajte [ovdje][anonymous].

Nadalje, skrivanje Bitcoin prometa Tor mrežom samo je donekle ostvarivo - Bitcoin, da bi ostao funckionalan, jednostavno **mora** imati barem nekoliko korisnika u javno dostupnom internet prostoru (dakle, ne-skriveno), pa stoga moramo računati na to da u barem jednoj zemlji Bitcoin mora ostati legalan i funckionalan ako želimo da globalno opstane. Tada nastupa novi problem - država, nakon što ih identificira, lako blokira promet prema tim ostalim Bitcoin čvorovima, i upadamo u tehnološku utrku s državom - tko će prije zaobići metode od onog drugog.

### Ilegalizacija

Drugi način je deklarirati rat na kriptovalute u obliku ilegalizacije. Odluči li vlada da se kriptovalute koriste samo za financiranje kriminala i/ili terorizma (što nije ni blizu istini), političari i bankari dobivaju pravo da kriptovalute proglase ilegalnima, i time ih guraju u "podzemlje". Tehnički sposobni korisnici i entuzijasti kriptovalute će i dalje koristiti nesmetano, no prosječni korisnik biti će opet izbačen iz sustava koji je tek počeo upoznavati.

![Ovdje ne primamo Bitcoin!](https://bitfalls.com/wp-content/uploads/2017/08/cryptocurrencies.png)

Također, budući da transakcije u blockchain protokolima mogu nositi neke podatke koje pošiljatelj sam pridodaje, a blockchain je nepromjenjiv - tj. potpuna povijest blockchaina je prisutna zauvijek i ne može se mijenjati u prošlost, kao što smo objasnili u [blockchain][blockchain] članku, moguće je uz transakcije poslati vrstu podataka koja se u pojedinoj zemlji smatra ilegalnom (pedofilija, piratski materijali, vladine tajne). Time bi se učinilo cijeli blockchain ilegalnim u toj zemlji - sama prisutnost tih podataka na blockchainu implicirala bi da je medij koji te podatke sadrži sada ilegalan za korištenje. Dapače, Bitcoinov blockchain već sadrži razna čudesa - od slike Nelsona Mandele do molitvi i čak poruka za valentinovo - [više info o svemu tome ovdje](http://www.righto.com/2014/02/ascii-bernanke-wikileaks-photographs.html).

### Resursi

Trenutno, za *rudarenje* Bitcoina potrebna je enormna količina struje. Ako se na državnoj razini povisi cijena struje ili identificira i blokira tip potrošnje (postoje [uređaji koji mogu identificirati trošila u električnoj mreži](https://ecoisme.com/)), rudarenje postaje u najbolju ruku neisplativo, u najgoru nemoguće. Dok neke kriptovalute kreću na drugačiju metodu stvaranja novčića, Bitcoin planira do daljnjega ostati na skupom, strujnom rudarenju, i tu mu je slaba točka - nestabilnost u električnoj mreži neke države može ozbiljno usporiti korištenje kriptovaluta u istoj.

![Mrtvo računalo ne može rudariti](https://bitfalls.com/wp-content/uploads/2017/08/giphy.gif)

Sva tri scenarija pretpostavljaju da vlada ima daleko više mašte, poduzetnosti, i spremnosti nego u stvarnosti. Pravi ubojica kriptovaluta bio bi potez koji uključuje sva tri napada, i to na razini Europe ako ne i šire. Budući da je većina modernih država već objeručke prihvatila kriptovalute (Zug u Švicarskoj je poznat kao _cryptovalley_, tj. svojevrsni raj za tvrtke koje svoj posao baziraju na blockchain tehnologijama, dok je Australija [priznala Bitcoin kao neoporezivu valutu](https://cointelegraph.com/news/australia-will-recognize-bitcoin-as-money-and-protect-bitcoin-businesses-no-taxes)) takav napad nije vjerojatan bez da se već u ovim ranim stadijima ozbiljno našteti brojnim revolucionarnim industrijama.


## Zaključak

Bitcoin nije nezaustavljiv, ali nije ni lak za zaustaviti. 

Dok nam je svima drago da se konačno borimo protiv banaka i lažno nametnutih vrijednosti, moramo biti realni i imati na umu da operiramo s relativnom slobodom isključivo jer nam to za sada vlada dopušta - u nekim državama zbog sporosti tehnologije u tom kraju svijeta (Hrvatska), u drugima pak jer su prednosti blockchain tehnologija jasno vidljive.

> Tek kad kriptovalute postanu _nezamijenjive_ postati će i _nezaustavljive_

Kako bismo uistinu pobijedili i učinili kriptovalute zaista nezaustavljivima, potrebno je širenje znanja o kriptovalutama i njihovo prihvaćanje od strane šire javnosti. Tek kad kriptovalute postanu _nezamijenjive_ postati će i _nezaustavljive_. Zato ne čekajte - [pridružite nam se čim prije][buy-cc].

[cryptocurrency]: /hr/2017/08/20/cryptocurrency/
[anonymous]: anonymous
[blockchain]: /hr/2017/08/20/blockchain-explained-blockchain-works/
[buy-cc]: buycrypto
