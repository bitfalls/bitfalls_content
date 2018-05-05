# Çfarë është Blockchain – Si Funksionon

Çfarë është *blockchain*?

  ![Imazhi kokë i blockchain](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-header.png)

Si funksionon, pse është kaq i famshëm, dhe pse shumë njerëz thonë se do ketë ndikim rrënjësor botëror?

Në këtë artikull, do të shpjegojmë teknologjinë e blockchain me një shembull banal i cili është i vlefshëm për pjesën dërrmuese të kriptomonedhave që janë në qarkullim. Shiko [këtu][coin]!

## Mario dhe Luigi

Mario do ti dërgojë $100 vëllait të tij, Luigit, sepse Luigi si Luigi, hyri në borxhe nga ana tjetër e botës.

  ![blockchain luigi me borxhe](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-01.png)

Mario futet në bankë dhe thotë “Do doja ti dërgoja $100 Luigit”. Bankieri i thotë “Kartën e llogarisë ju lutem.”, “Kartë identiteti ju lutem” dhe “u krye”, në këtë rradhë.

  ![mario duke lare borxhet](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-02.png)

Në këtë skenar të *centralizuar*, banka është autoriteti ***ekzekutiv*** mbi paratë e Marios dhe Luigit. Të dy, dhe Mario dhe Luigi i besojnë bankës dhe besojnë në numrat që tregojnë deklaratat e llogarisë. Ata i besojnë bankës pavarësisht faktit se bankës i duhet thjesht – të ndryshojë një numër në databazë. Gjithcka është dixhitale në fund të fundit.

Megjithatë, kur jemi të varur nga një autoritet i centralizuar, ky autoritet na vë përpara një shqetësimi. Ai mund të zhduket me të gjitha paratë, mund të jetë i ligë dhe mos t’ia shtojë paratë Luigit ndërkohë që ia ul Marios, në këtë mënyrë e mban diferencën, ose mund të jetë i ngathët dhe të kryejë ndonjë gabim të këtij lloji. Pra, financat tona varen direkt nga kompetenca e tyre.

  ![Hajduti](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-03.png)

Një mënyrë për ta parandaluar këtë skenar të ndodhë është anashkalimi komplet i bankës dhe të pasurit një sistem tonin gjurmues ndaj vlerës së dërguar dhe rrugëtimit të saj nga një vënd në një tjetër.

  

Imagjino një copë letër ku ne shënojmë gjëndjen e llogarisë sonë bankare. Në qoftë se vetëm Mario dhe Luigi e përdorin këtë sistem, është e vështirë të ketë drejtësi – sepse në momentin që dikush bëhet lakmitar, sistemi kompromentohet. Prandaj, një sistem i tillë i *deçentralizuar* duhet të ketë mjaftueshëm pjesëmarrës për ta bërë të zbatueshëm – të paktën tre persona.

## **Letrat**

Le të hamendësojmë se kemi 5 pjesëmarrës: Yoshi, Mario, Luigi, Wario, dhe Bowser, dhe se secili prej tyre ka nga një copë letre.

  ![miners](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-04.png)

Mario do ti dërgojë $100 dollarë Luigit. Për ta bërë këtë, ai ia bën të ditur të gjithëve (me zë lartë): “Po i dërgoj Luigit $100 dollarë! Ju lutem mbani të gjithë shënim!”

![transferta](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-05.png)

Në atë moment, cdo pjesëmarrës kontrollon llogarinë e Marios për tu siguruar që ai ka mjaftueshëm para në të për t’ja dërguar Luigit (po, çdo gjëndje llogarie është publike) dhe nëse është ashtu, e shkruajnë këtë transfertë në letrat e tyre. Transfertat e ketij lloji shkruhen në fletat e cdo pjesëmarrësi deri në momentin që s’ ka më vend. Në fjalë të tjera, **çdo** transfertë ndërmjet ****çdo dy** njerëzve** është e regjistruar në **letrën e çdo pjesëmarrësi**.

Përpara se ta arkivojmë letrën e mbushur në një dosje apo në një kabinet dhe të marrim një letër të re, një letër bosh, duhet ta vulosim letrën e mbushur me një kod special.

## Vulat dhe Mining

Kjo “vulë” garanton se përmbajtja e letrës është e vërtetë.

Si mund ta marrim këtë vulë? Me një algoritëm të veçantë të cilit, kur i japim disa të dhëna inputi, gjithmonë jep rezultat të njëjtë nëse inputi është i njëjtë.

Marrim shembullin e mëposhtëm:

X1 + X2 + … Xn = Z.

Në fjalë të tjera, një mbledhje e thjeshtë.

Le të supozojmë se vlerat e letrave tona janë të vërteta dhe të vlefshme (të gjitha transfertat janë të kombinuara) në qoftë se dhe vetëm një veprim mbledhjeje jep numrin 10000.

1000 + 6000 + 3000 = 10000.


Në këtë rast, inputi është 1000, 6000, dhe 3000, ndërkohë vula është 10000.

Në rregull, le të supozojmë se pjesëmarrësit tanë më sipër arritën në një marrëveshje: nëse, kur mbledh të gjitha numrat në letër dhe një kombinacion specifik tjetër numrash, dhe rezultati është 10000, atherë transfertat në atë letër janë të vlefshme dhe mund të konsiderohen si të konfirmuara.

Për shembull, nëse letra përmban këto 5 transfertat e mëposhtme:

-   Mario → Luigi = 100
    
-   Bowser → Yoshi = 200
    
-   Yoshi → Luigi = 100
    
-   Mario → Yoshi = 500
    
-   Luigi → Wario = 100
      

Shuma është 1000, pra ne po kërkojmë për një numër që jep 10000 kur e mbledhim me 1000. Mbetja është 9000 mund të arrihet me shumë kombinacione:


-   5000 + 4000
    
-   1000+ 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000
    
-   2000 + 3000 + 2000 + 2000
    
-   etj…
    

Kompjuteri është aq i zgjuar sa në mënyrë intuitive ta dallojë se cilat numra do rezultojnë në numrin e dëshiruar. Për ta arritur këtë rezultat kompjuteri duhet të supozojë midis kombinacioneve të ndryshme nën 10000 deri në momentin që gjen një kombinacion i cili prodhon 10000. Kështu që pjesëmarrësi i parë që gjen kombinacionin e saktë të numrave që japin 10000 kur mblidhen me gjithë transfertat në letër do jetë ai i cili ja tregon gjithë të tjerëve rezultatin.


Supozojmë se Yoshi gjeti kombinacionin 4000 + 5000. Dhe i thotë të gjithëve: “ E gjeta kombinacionin! Provoni 4000 dhe 5000!” Duke qënë se është shumë e thjeshtë ta vërtetosh saktësinë e numrave të Yoshit duke i futur në algoritëm, pjesëmarrësit e tjerë e vërtetojnë këtë. Të gjithë pjesëmarrësit, të cilët gjatë kontrrollit, kanë po të njëjtën vlerë 10000 kur e mbledhin me 4000 dhe 5000 japin vlefshmërinë e këtyre transfertave. Duke bërë këtë, arrihet në një konsensus që letrat janë të vlefshme.

Nëse letrat e njërit prej tyre nuk japin rezultatin 10000 kur i mbledh me 4000 dhe 5000 ka një problem. Nëse, marrim si shembull Bowser dashje padashje ka regjistruar një tjetër transfertë – le të themi, Mario i dha Luigit $200, dhe jo $100 – atherë shuma nuk do përputhej me kërkesat.

![shpjegimi i blockchain ](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-07.png)

Në këtë mënyrë letra e Bowserit konsiderohet jo e vlefshme, dhe nëse ai do të vazhdojë të jetë pjesëmarrës në këtë sistem, atij i duhet ta hedhi letrën e vjetër, të kopjojë letrën e saktë të dikujt tjetër, dhe të premtojë që në të ardhmen do jetë më i kujdesshëm. Nga ana tjetër Yoshi, i cili ishte ai që gjeti kombinimin fitues, merr një shpërblim, për shembull, $5 nga sistemi. Sistemi _prodhon_ $5 dollarë nga hiçi si shpërblim për këtë pjesëmarrës me fat.

![yoshi fitues](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png)

Ky _prodhim_  parash nga hici quhet _mining_ në botën e kriptomonedhës.


Ndërkohë që ky ishte një shembull shumë i thjeshtëzuar, i vetmi ndryshim  në eksperiencën reale të blockchain (përveç faktit që në të vërtetë gjithçka është dixhitale dhe automatike) është fakti se algoritmi që përdoret për të prodhuar vulën është ndryshe – pra më i komplikuar dhe që mund të pranojë si numra dhe gërma, dhe kode të tipit:

`90bdaa79bbccacf8558edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`.

![hash](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-06.png)

Këto _vula_ quhen _hashes dhe algoritmet_ të cilat i gjenerojnë këto – si SHA256 i cili prodhoi kodin më sipër – janë quajtur _hashing functions._ Provoni të hapni [këtë link](http://www.xorbin.com/tools/sha256-hash-calculator) dhe të fusni një tekst të cfarëdoshëm në hapsirën e dhënë. Nëse fusni një fjalë të vetme ose gjithë biblën, ajo do gjenerojë gjithmonë një kod prej ekzaktësisht 64 karakteresh.

Prandaj për të marrë numrin (hash) që vulos letrat tona, ne fusim në algoritëm të gjitha transfertat që ndodhen në letër. Ato kthehen në hash. Duke qënë se ka një numër infinit kombinimesh të karaktereve që mund të fusim në algoritëm, të supozuarit të të dhënave paraprake bazuar mbi kodin hash është matematikisht e pamundur. 

Specifikisht, në blockchainin e Bitcoinit, marrëveshja midis netuorkut dhe pjesëmarrësve të jetë e tillë që, për sa kohë një hash i prodhuar (të cilin mund ta marrim duke kombinuar hashin e letrës së fundit me transaksionet e letrës aktuale, plus numra dhe gërma të rastësishme) fillon me një numër të caktuar zerosh ai është i vlefshëm. Për shëmbull, nëse letra 1 ka hashin:

`0000000000000000058edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`

atëherë hashi i vlefshëm i letrës 2 do jetë ai i cili ka të njejtin numër zerosh në fillim, ose më shumë.

Për të marrë këtë kombinacion të rastësishëm karakteresh të nevojshme për të prodhuar një hash të vlefshëm, kompjuteri duhet të hamendsojë. Kompjuterat modernë janë shumë të shpejtë dhe lehtësisht provojnë mijra kombinime në sekondë, por kjo prap nuk është e mjaftueshme duke marrë parasysh se mundësitë e kombinimeve janë afër infinitit. Konkluzioni është se, vështirësia për të supozuar një hash të ri është e rendit 17, sepse ka 17 zero në fillim të tij. Me kalimin e kohës, vështirësia do të rritet dhe një hash i vlefshëm do t'i duhet shumë e më shumë zero në fillim. 

Kur letra e çdo pjesëmarrësi shënohet si e vlefshme me hashin e ri, vihet në një dosje – ose një libër llogarish le të themi, dhe mbas kësaj tërhiqet një letër e bardhë.

## **Terminologjia e Blockchain**

Në terminologjinë e blockchain...

 - një letër është _a block_ (një bllok).
 - një bllok përmban shumë _transferta_
 - një bllok është gjithmonë pasardhës i një blloku primar, duke formuar një _chain_ (zinxhir). Një bllok zinxhirash nga vjen dhe fjala _blockchain_. Blloqet e verifikuara vihen anash në një libër llogarish (sinonim me blockchain).
 - procesi i të hamendësuarit të kombinacioneve quhet _nodes_ (nyje). Një nyje që zgjidh kombinacionin e hash-it merr një shpërblim në formën e tokens-ave të blockchain - në shembullin tonë Bitcoin.
 - Procesi i hamendësimit të kombinacionit quhet mining (gërmim) sepse ne jemi duke gërmuar për një vlerë në një tufë me mundësi. Në vend të muskujve dhe matrapikut për këtë proces, përdorim elektricitet, kohë, dhe fuqinë llogaritëse të kompjuterit. Karakteret që i morë si shembull pak më sipër janë të gjithë sipër makinave me gara sepse në të vërtetë ky proçes është tamam një garë - ai i cili konfirmon një hash të vlefshëm për një bllok specifik fiton, dhe merr në fund shpërblimin e vlefshëm. E njëjta gjë ndodh në botën e blockchain-it, kompjuterat me fuqinë proçesuese më të madhe zakonisht fitojë shpërblimet e bllokut. 
 - Krijimi i një hashi të ri quhet **proof of work**. Ky është një model që përdorin shumë kriptomonedha në mënyrë që hamendësimi i numrave dhe hilet financiare të mos jenë praktike për shaka se ky proçes ka kosto të larta elektricikteti. Disa protokolle si Ethereum kanë përshatur sistemin **proof of stake** ku po minimizohet harxhimi i energjisë së kotë dhe pjesëmarrjet e gënjeshtërta ndëshkohen, por kjo është temë për një tjetër diskutim. 


## **Konkluzioni**

Të gjitha kriptomonedhat janë të bazuara në teknologji blockchain. Blockchain bën të mundur që ato të jenë transparente, të pa falsifikueshme dhe deri diku të limituara në sasinë maksimale të prodhimit. Në të kundërt nga valuta fiat (USD, Euro, etj.) kriptomonedhat nuk mund të printohen nga krijuesit e tyre, përveç në raste të tipit si monedhat mashtrim si Ripple (XRP) ose OneCoin – më shumë për këto në postime të tjera

Teknologjia Blockchain lejon kontroll të shpërndarë të sistemit financiar të një shoqërie – lokale ose globale – dhe eleminon një ndërmjetës si në rastin e bankave. Kjo është një prej arsyeve kryesore se pse [kriptomonedhat][coin] kanë bërë kaq shumë bujë. Në sajë të kësaj mënyre të deçentralizuar të blockchain dhe miliona përdoruesve të cilët shërbejnë si llogaritar dhe vërtetues, shumë njerëz i konsiderojnë kriptomonedhat si të pa shkatërueshme dhe të pandalshme. Fatkeqësisht, kjo është një iluzion, të cilin do ta sqarojmë më vonë. (shiko linket në seksionin më poshtë)

## Po më pas?

 - [Cfarë janë kriptomonedhat][coin] - informohu mbi to dhe nga vjen vlera e tyre
 - [Bitcoin është i pandalshëm][unstop] - për të kuptuar sa e thjeshtë është ti japësh fund një kritpomonedhe
 - [Bitcoin ka një limit][finite] - për të mësuar pse limiti teorik prej 21 milion Bitcoin të prodhuar, praktikisht nuk është i vërtetë
 - [Bitcoin nuk është anonim][anon] - mëso pse njerëzit (gabimisht) thonë se Bitcoin është anonim dhe se përdoret për tregun e zi dhe financim kriminal
 - [Cfarë është Ethereum?][eth]- informohu rreth kriptomonedhës më të fuqishme dhe ngjashmëritë dhe ndryshimet që ka me Bitcoin 

[coin]: https://bitfalls.com/2017/08/20/cryptocurrency/

[unstop]: https://bitfalls.com/2017/08/21/is-bitcoin-unstoppable/

[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/

[anon]: https://bitfalls.com/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/

[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/


