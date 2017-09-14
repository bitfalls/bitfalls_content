Kada pišete članke za Bitfalls.com, predlaže se praćenje sljedećih smjernica za najbolje rezultate. Dobro napisani i gramatički ispeglani članci s solidnom strukturom biti će editirani brže od ostalih.

## Naslovi i podnaslovi

Naslov članka će odrediti urednik jer optimizacija za tražilice ima prioritet, no osjećajte se slobodnima predložiti vlastitu ideju i biti će uzeta u obzir.

Najviši heading u članku je H2, to znači `##`. Drugim riječima, `#` (H1) ne smije postojati, on je rezerviran za naslov članka. Podnaslovi sekcija su `##` (H2), podnaslovi u njima `###` (H3), i podnaslovi u njima `####` (H4) ili bullet points (`•`). Maksimalna dubina je H4 (`####`).

Naslovi i podnaslovi **moraju** imati razmak između oznake naslova i samog naslova, tj. `##Naslov` vs. `## Naslov`.

## Uvod i zaključak

Svaki članak (koji nije vijest) trebao bi imati kratak uvod (1 paragraf) koji objašnjava što će čitatelj naučiti i koje je potrebno predznanje. Kod listanja predznanja, preporučljivo je staviti poveznice na ostale članke na Bitfalls koji objašnjavaju isto.

Svaki članak trebao bi imati zaključak u kojem se kratko rezimira što smo naučili - posebice tehnički članci koji se bave programiranjem ili objašnjenjem tehničkih pojmova. Zaključak ne bi smio imati više od 2 odlomka i mora biti H2: `## Zaključak` (a ne `Da rezimiramo` ili `Što smo naučili` itd.).

## Linkovi u Markdownu

Stavite linkove na dno članka, a referencirajte ih u tekstu skraćenim oblicima, ovako:

```
Ovo je neki markdown tekst, i ima [link][nekilink] ovdje. Ovdje se ponavlja [isti link][nekilink].

...

[nekilink]: https://mojlink.com/
```

To omogućava lako baratanje linkovima za vrijeme prevođenja članka, i poboljšava čitljivost samog članka za vrijeme pisanja i peer reviewa, kad je još u Markdown stadiju.

Za primjer, pogledajte source (raw gumb u sučelju) ovog dokumenta, i skrolajte do dna.
  
## Alati

Za pisanje Markdown članaka, preporučljivo je koristiti specijalizirane programe poput [Caret.io][caret], MacDown na Mac OS sustavima, i slično. Dobri online editori su Stackedit i Dillinger. Bitno je za vrijeme pisanja imati upaljen preview mode, ili barem napraviti preview prije slanja članka, kako bi se provjerilo da se ništa ne raspada prilikom prikazivanja.

Za provjeru gramatike kad se piše na engleskom jeziku, Grammarly je OK usluga. Korištenje osnovnog spell checkera je obavezno kod engleskog jezika.

## Slike

Ako članak treba neke slike (preporučljivo je razbiti zid teksta grafovima i slikama), slike moraju biti public domain - znači bez licence i slobodne za korištenje za bilo koju svrhu - ili imati pisanu dozvolu autora da se ta slika koristi na sajtu.

Slike se stavljaju u `images` mapu pored jezične mape članka, pa tako ako se piše članak na hrvatskom jeziku, struktura izgleda ovako:

    - 01-clanak/
        - hr_HR/
          - final.md
        - images/
          - 01.jpg
          
Slike treba imenovati brojčano prema poziciji u članku, radi lakšeg dodavanja u sustav prilikom publikacije. Glavna slika koja će služiti kao thumbnail i header treba se zvati `header` i imati ekstenziju `.jpg`, `.png`, ili `.gif`.

## Povezivanje sadržaja

Gdje je to moguće, obavezno povezati sadržaj s drugim člancima na stranici. Primjerice, ako neki članak spominje riječ blockchain, povezati tu riječ sa [ovim člankom][blockchain]. Ako se spominje pucanje bitcoin mjehura, povezati s [ovim člankom][bubble], itd. Bitno je pritom paziti na jezik povezanog članka - primjetite `/hr/` u URLu ovih članaka - povezujte članke na one koji su na istom jeziku kao taj kojeg pišete.

Kada je to prikladno (ne uvijek, i ne često), spomenite proizvode iz našeg web shopa i ubacite poveznice na iste. Ne treba pretjerivati, no povremeno dobro dođe - prodaja iz web shopa, uz prodaju kriptovaluta i konzultacije oko istih, je kako se Bitfalls financira i iz toga će izlaziti plaće za autore - više prodaja znači više kapaciteta za objavljivanje sadržaja, što znači više posla za autore.

## Zamjenice

Članci moraju biti objektivni i neutralni gdje god je to moguće, osim u iznimnim slučajevima kada se piše editorial ili kada objavljujemo kolumne. Stoga treba izbjegavati riječ "ja" i fokusirati se na "vi" ili "mi". Kada odaberete jedno, držite se toga. Npr., umjesto:

_"U ovom ću primjeru pokazati kako je najbolje spojiti metodu iz pametnog ugovora s vanjskim API. Nakon toga, znati ćete kako to učiniti u svojim projektima."_

Pravilnije bi bilo:

_"U ovom ćemo primjeru spojiti metodu iz pametnog ugovora s vanjskim API. To će nam olakšati taj proces u budućim vlastitim projektima."_

Za ostale korisne savjete, pogotovo ako pišete tehnički članak, pročitajte [ovaj odlični vodič][guide].

## Kod

Kad pišete kod, obavezno ga omeđite trostrukim obrnutim apostrofima, tzv. _code fencing_ s napomenom jezika o kojem se radi. Više detalja o tome [ovdje][codefence].

        ```solidity
        struct Voter {
                uint weight; // weight is accumulated by delegation
                bool voted;  // if true, that person already voted
                address delegate; // person delegated to
                uint vote;   // index of the voted proposal
            }
        ```
   
## Što ne raditi

- ne koristiti referral linkove.
- ne tražiti donacije, ne stavljati svoju kripto adresu u članke.
- ne direktno savjetovati kupnju neke kriptovalute (npr. "Mislim da se isplati kupiti jer će rasti u vrijednosti"). Bitfalls nije investicijski savjetnik, i najviše što smijemo je neformalno predložiti ili upozoriti na neke stvari u obliku osvrta u člancima.
        
[caret]: https://caret.io
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[bubble]: https://bitfalls.com/hr/2017/09/06/bitcoin-bubble/
[guide]: https://www.impressivewebs.com/how-to-write-great-web-development-articles-tutorials/
[codefence]: https://help.github.com/articles/creating-and-highlighting-code-blocks/