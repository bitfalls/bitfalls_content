Ovog utorka (12.3.2018.) [Coinbase][Coinbaselink] je objavio novi alat ugrađen u web sučelje burze. Od sada je moguće pratiti cjelokupnu aktivnost trgovanja koju je korisnik obavio u određenom vremenskom periodu (najčešće od 1.1.xx. do 31.12.xx. koliko traje poslovna godina).

Alat funkcionira na način da korisnici generiraju izvješće o obavljenoj trgovini na svojem Coinbase računu. Izvješće sadrži svu kupovinu, prodaju i slanja kriptovaluta unutar Coinbase računa uključujući i troškove transakcija.
Na taj način [Coinbase][Coinbaselink] omogućuje korisnicima lakše praćenje ulaganja i trgovanja te na kraju prijavu poreza. Način na koji se obračunava dobit ili gubitak jest da se od iznosa prihoda oduzmu rashodi i tako dobije iznos dobiti ili gubitka. Logično je da se na gubitak ne plaća porez, no na dobit se obračunava porez u iznosu od 12% plus prirez prema članku zakona o porezu na dohodak. [Zakon čl. 70][zakonlink]

"Člankom 70. Zakona propisan je način utvrđivanja i plaćanja poreza na dohodak od kapitala te je porezni obveznik – imatelj financijske imovine sam obvezan porez na dohodak od kapitala po osnovi kapitalnih dobitaka, obračunati, obustaviti i uplatiti do posljednjeg dana mjeseca veljače tekuće godine za sve kapitalne dobitke ostvarene u prethodnoj godini, umanjene za ostvarene kapitalne gubitke. Porez se plaća po stopi od 12%, a koji se potom uvećava za prirez koji propišu općine i gradovi. Porez plaćen po osnovi kapitalnih dobitaka smatrat će se konačnim, što znači da se neće uzeti u obzir u godišnjem obračunu poreza na dohodak i da porezni obveznik po toj osnovi neće morati podnijeti godišnju poreznu prijavu, ali ni moći ostvariti povrat, kao ni veću razliku za uplatu"

Važno je naglasiti da ovaj način izračunavanja poreza koristi isključivo korisnicma [Coinbasea][Coinbaselink] koji su trgovali samo na toj burzi jer ista ne prati prihode i rashode s drugih burza koje je važno uključiti u izvještaj. Pa tako navode na blogu da ne koristite alat ako ste:
- Trgovali na drugim burzama
- Slali i primali sredstva s drugih burza na [Coinbase][Coinbaselink] wallet (uključujući i GDAX)
- Držali kriptovalute na hardware walletima poput Trezora i Ledgera
- Ulagali u ICO
- Prethodno koristili drugi način knjiženja, različit od [Fifo metode][fifolink] metode (First in first out)

Koraci za generiranje izvještaja su sljedeći:

1.	U kartici Tools odaberite karticu Reports i kliknite na + New Report kao što je vidljivo na slici ispod:

![slika1]


2.	Nakon toga odaberete vrstu izvještaja koji želite. 
Type: Cost Basis for Taxes (BETA)
Account za koji želite report (BTC, ETH, LTC ili BCH)
Time range: godina za koju želite izvještaj
Email to: mail na koji želite da se dostavi izvještaj

3.	Kao posljednji korak kliknite na Create Report.
![slika2]

4.	Na email koji ste upisali stiže Excel tablica s traženim podacima, no isti se može skinuti direktno sa [Coinbase][Coinbaselink] report liste. U Excelu je detaljno prikazana svaka transakcija, no na vrhu je vidljiva ukupna razlika prihoda i rashoda koja je bitna za izračun plaćanja poreza.

![slika3]

U našem primjeru vidljivo je kako je ukupno na Bitcoin potrošeno $710, ukupno prodano Bitcoina u vrijednosti $794 te je ukupna dobit $84.5. Na taj iznos obračunavamo 12% poreza te dolazimo do iznosa od $10.14. Na iznos od $10.14 stanovnici grada Zagreba plaćaju [prirez][prirezlink] u iznosu od 18% koji na $10.14 iznosi $1.82. Ukupan iznos koji je ostao korisniku nakon plaćanja poreza iznosi $72.54.

Iz svega navedenog zaključuje se kako je alat dobar korak unaprijed pri pojednostavnjenju prijave poreza no samo korisnicima kojima je jedina investicija kupovina i prodaja kriptovaluta na [Coinbaseu][Coinbaselink], a ne i na ostalim burzama.

[Coinbaselink]:httpss://www.coinbase.com
[zakonlink]:https://www.zakon.hr/z/85/Zakon-o-porezu-na-dohodak
[fifolink]:http://www.ep.hr/help/fifo_metoda.htm
[prirezlink]:https://www.porezna-uprava.hr/HR_porezni_sustav/Stranice/prirez_porezu_na_dohodak.aspx
[slika1]:https://raw.githubusercontent.com/nikolaposloncec/bitfalls_content/nposloncec-00-coinbse-tax/authors/nposloncec/00-coinbase-tax-tool/images/pic1.1.png
[slika2]:https://raw.githubusercontent.com/nikolaposloncec/bitfalls_content/nposloncec-00-coinbse-tax/authors/nposloncec/00-coinbase-tax-tool/images/pic2.1.png
[slika3]:https://raw.githubusercontent.com/nikolaposloncec/bitfalls_content/nposloncec-00-coinbse-tax/authors/nposloncec/00-coinbase-tax-tool/images/pic3.1.PNG



