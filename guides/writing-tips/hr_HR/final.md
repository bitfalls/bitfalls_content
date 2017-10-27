Sljedeći savjeti će drastično ubrzati vrijeme uređivanja članaka zbog manje potrebne komunikacije između autora i urednika. Uzmitei ih u obzir i ukomponirajte u vlastiti stil pisanja.

## Savjet 1: Naslovi i podnaslovi

Naslov članka će odrediti urednik jer optimizacija za tražilice ima prioritet, no osjećajte se slobodnima predložiti vlastitu ideju i biti će uzeta u obzir.

Najviši heading u članku je H2, to znači `##`. Drugim riječima, `#` (H1) ne smije postojati, on je rezerviran za naslov članka. Podnaslovi sekcija su `##` (H2), podnaslovi u njima `###` (H3), i podnaslovi u njima `####` (H4) ili bullet points (`•`). Maksimalna dubina je H4 (`####`).

Naslovi i podnaslovi **moraju** imati razmak između oznake naslova i samog naslova, tj. `##Naslov` vs. `## Naslov`.

## Savjet 2: Uvod i zaključak

Svaki članak (koji nije vijest) trebao bi imati kratak uvod (1 paragraf) koji objašnjava što će čitatelj naučiti i koje je potrebno predznanje. Kod listanja predznanja, preporučljivo je staviti poveznice na ostale članke na Bitfalls koji objašnjavaju isto.

Svaki članak trebao bi imati zaključak u kojem se kratko rezimira što smo naučili - posebice tehnički članci koji se bave programiranjem ili objašnjenjem tehničkih pojmova. Zaključak ne bi smio imati više od 2 odlomka i mora biti H2: `## Zaključak` (a ne `Da rezimiramo` ili `Što smo naučili` itd.).

## Savjet 3: Linkovi u Markdownu

Stavite linkove na dno članka, a referencirajte ih u tekstu skraćenim oblicima, ovako:

```
Ovo je neki markdown tekst, i ima [link][nekilink] ovdje. Ovdje se ponavlja [isti link][nekilink].

...

[nekilink]: https://mojlink.com/
```

To omogućava lako baratanje linkovima za vrijeme prevođenja članka, i poboljšava čitljivost samog članka za vrijeme pisanja i peer reviewa, kad je još u Markdown stadiju.

Za primjer, pogledajte source (raw gumb u sučelju) ovog dokumenta, i skrolajte do dna.
  
## Savjet 4: Alati

Za pisanje Markdown članaka, preporučljivo je koristiti specijalizirane programe poput [Caret.io][caret], MacDown na Mac OS sustavima, i slično. Dobri online editori su Stackedit i Dillinger. Bitno je za vrijeme pisanja imati upaljen preview mode, ili barem napraviti preview prije slanja članka, kako bi se provjerilo da se ništa ne raspada prilikom prikazivanja.

Za provjeru gramatike kad se piše na engleskom jeziku, [Grammarly](https://www.grammarly.com) je OK usluga. Korištenje osnovnog spell checkera je obavezno kod engleskog jezika.

## Savjet 5: Slike

Ako članak treba neke slike (preporučljivo je razbiti zid teksta grafovima i slikama), slike moraju biti public domain - znači bez licence i slobodne za korištenje za bilo koju svrhu - ili imati pisanu dozvolu autora da se ta slika koristi na sajtu.

Slike se stavljaju u `images` mapu pored jezične mape članka, pa tako ako se piše članak na hrvatskom jeziku, struktura izgleda ovako:

    - 01-clanak/
        - hr_HR/
          - final.md
        - images/
          - 01.jpg
          
Slike treba imenovati brojčano prema poziciji u članku, radi lakšeg dodavanja u sustav prilikom publikacije. Glavna slika koja će služiti kao thumbnail i header treba se zvati `header` i imati ekstenziju `.jpg`, `.png`, ili `.gif`.

## Savjet 6: Duljina članka i članci od više nastavaka

Optimalne su sljedeće duljine (moguće su iznimke):

- novosti: 200 - 500 riječi
- vodič: do 1200 riječi
- tehnički vodič ili tutorial programiranja: do 2000 riječi

Kod se ne broji.

Ako je neki članak dovoljno opsežan da prelazi 2000 riječi, moguće je podijeliti ga u part 1 i part 2. Maksimalni broj dijelova koji će članak imati je 2. Ako se radi o više, pretvaramo ga u serijal u kojem svaki dio treba biti čim samostalniji - moderna publika gubi interes kada vidi previše povezanih dijelova koji ovise jedni o drugima. Ti pojedinačni dijelovi moraju biti čitljivi kao neovisni članci, ali mogu referencirati ostale.

## Savjet 7: Brojevi

Brojevi do 10 trebaju biti ispisani slovima, osim ako ne označavaju entitet koji se koristi samo u numeričkom smislu, poput valute. Npr.:

- "Pojeo sam šest sendviča" je bolje od "Pojeo sam 6 sendviča"
- "Kupio sam 2 Eth" je bolje od "Kupio sam dva Eth"

## Savjet 8: Povezivanje sadržaja

Gdje je to moguće, obavezno povezati sadržaj s drugim člancima na stranici. Primjerice, ako neki članak spominje riječ blockchain, povezati tu riječ sa [ovim člankom][blockchain]. Ako se spominje pucanje bitcoin mjehura, povezati s [ovim člankom][bubble], itd. Bitno je pritom paziti na jezik povezanog članka - primjetite `/hr/` u URLu ovih članaka - povezujte članke na one koji su na istom jeziku kao taj kojeg pišete.

Kada je to prikladno (ne uvijek, i ne često), spomenite proizvode iz našeg web shopa i ubacite poveznice na iste. Ne treba pretjerivati, no povremeno dobro dođe - prodaja iz web shopa, uz prodaju kriptovaluta i konzultacije oko istih, je kako se Bitfalls financira i iz toga će izlaziti plaće za autore - više prodaja znači više kapaciteta za objavljivanje sadržaja, što znači više posla za autore.

### Povezivanje eksternog sadržaja

Potrebno je koristiti poveznice na vanjski sadržaj, pogotovo kod citiranja. Jeste li znali da je moguće stavljati poveznice i na specifične dijelove teksta? Isprobajte Chrome ekstenziju poput [TLDRify](https://chrome.google.com/webstore/detail/tldrify/dbphpdgmhigmaepjklmklmlcoinihjdo/reviews?hl=en) za tu funkcionalnost kako biste čitateljima dali do znanja *točno* na koji dio teksta mislite.

Kad god je to moguće, koristite uslugu za arhiviranje web stranica poput [Archive.is](http://archive.is). To je prilično korisno kada se istražuju prijevare, obećanja projekata, i slično - uglavnom, sadržaj koji bi se kasnije mogao promijeniti.

## Savjet 9: Zamjenice

Članci moraju biti objektivni i neutralni gdje god je to moguće, osim u iznimnim slučajevima kada se piše editorial ili kada objavljujemo kolumne. Stoga treba izbjegavati riječ "ja" i fokusirati se na "vi" ili "mi". Kada odaberete jedno, držite se toga. Npr., umjesto:

_"U ovom ću primjeru pokazati kako je najbolje spojiti metodu iz pametnog ugovora s vanjskim API. Nakon toga, znati ćete kako to učiniti u svojim projektima."_

Pravilnije bi bilo:

_"U ovom ćemo primjeru spojiti metodu iz pametnog ugovora s vanjskim API. To će nam olakšati taj proces u budućim vlastitim projektima."_

Za ostale korisne savjete, pogotovo ako pišete tehnički članak, pročitajte [ovaj odlični vodič][guide].

## Savjet 10: Kod

Kad pišete kod, obavezno ga omeđite trostrukim obrnutim apostrofima, tzv. _code fencing_ s napomenom jezika o kojem se radi. Više detalja o tome [ovdje][codefence].

        ```solidity
        struct Voter {
                uint weight; // weight is accumulated by delegation
                bool voted;  // if true, that person already voted
                address delegate; // person delegated to
                uint vote;   // index of the voted proposal
            }
        ```
        
## Savjet 11: Ozbiljnost

Biti ozbiljan ne znači biti dosadan. Oslanjamo se na vrijednost našeg sadržaja da zarobi pažnju naših čitatelja, a ne milenijalske fraze.

- "Dakle, uskoro kreće Bitcoin Silver. WTF pak je to sad?"

Ovakvo izražavanje pripada na clickbait portale poput Index.hr, Telegram, Buzzfeed ili Boredpanda. Kod nas je cilj pokazati notu ozbiljnosti i zrelosti. Cilj je potaknuti znatiželju naših čitatelja bez da izgledamo kao da imamo 12 godina.

- "Bitcoin Silver uskoro izlazi. Možda ste se pitali odakle dolazi, zašto, i tko ga gura? U ovom članku ćemo sve to objasniti."

Ovaj blago žurnalistički ton potiče znatiželju u prosječnom čitatelju (naša ciljana publika) više od milenijalskog "wtf" tona. Daje notu zrelosti publikaciji i ostavlja dojam da je u pisanje članka uloženo više truda, a ne da je samo brzo sklepani prijevod vijesti s Reddita (na što se većina modernih publikacija svodi).

## Savjet 12: Pravilo trojke

Prije nego pošaljete skicu članka u repozitorij, učinite sljedeće:

1. pročitajte cijeli članak pažljivo
2. ako naiđete na bilo kakvu potrebu za izmjenom (greška u pisanju, krivo posložena fraza ili izražaj, slika kojoj nedostaje opis), napravite izmjenu i počnite čitati ispočetka.
3. `while (broj čitanja < 3) {goto 1}`

Drugim riječima, tako dugo dok članak ne možete pročitati od početka do kraja dok ne napravite **ni jednu izmjenu**, ne šaljite članak jer još nije spreman.

Zapamtite - puno ljudi čita vaš rad. Budite svoj najgori kritičar!

**Dodatni savjet:** Za najbolji rezultat, uzmite si pauzu između čitanja. Prilikom čitanja nečega s čime ste upoznati, mozak će nerijetko sam preskočiti materijal jer je upoznat s istim, i ignorirati greške - doslovno ih sakriti od vaših očiju. Više informacija o tim iluzijama [ovdje](https://cogsci.stackexchange.com/questions/13946/why-does-the-brain-skip-over-repeated-the-words-in-sentences).
   
## Što ne raditi

- ne koristiti referral linkove.
- ne tražiti donacije, ne stavljati svoju kripto adresu u članke.
- ne direktno savjetovati kupnju neke kriptovalute (npr. "Mislim da se isplati kupiti jer će rasti u vrijednosti"). Bitfalls nije investicijski savjetnik, i najviše što smijemo je neformalno predložiti ili upozoriti na neke stvari u obliku osvrta u člancima.
        
[caret]: https://caret.io
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[bubble]: https://bitfalls.com/hr/2017/09/06/bitcoin-bubble/
[guide]: https://www.impressivewebs.com/how-to-write-great-web-development-articles-tutorials/
[codefence]: https://help.github.com/articles/creating-and-highlighting-code-blocks/