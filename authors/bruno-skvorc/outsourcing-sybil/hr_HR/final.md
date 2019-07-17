DAO je "decentralizirana autonomna organizacija". To možda zvuči zastrašujuće, no radi se o jednostavnom programu na blockchainu kojime ne upravlja administrator ili direktor već članovi te organizacije. Tipično se odluke donose kroz glasanja, a jačina nečijeg glasa ovisi o tome koliko je investiran u tu zajednicu (pologom, sudjelovanjem, ugledom, itd.)

Prilikom izgradnje [Blockada DAO-a](https://blockada.io/dao), htjeli smo biti sigurni da su svi članovi ljudi a ne razne Ethereum adrese istog vlasnika. Taj je problem poznat kao _otpornost na Sybil napade_, tj. otpornost na lažno predstavljanje jedne osobe kao više različitih. To nam je bilo bitno jer se naš DAO bavi financiranjem blockchain događaja i druženja, i takav bi sustav bilo prelako manipulirati bez barem neke razine pouzdanosti u identitet članova.

[MolochDAO](https://molochdao.org), popularni DAO za financiranje [Ethereum 2.0 projekata](https://bitfalls.com/tag/two-point-oh/) zaobilazi taj problem na dva načina:

a) zahtijeva od svojih članova da polože značajnu količinu Ethera kao garanciju za nečije članstvo i

b) sprječava prijave od strane novih članova - nove članove moraju predložiti postojeći.

Ti su pristupi odlični kada želite manji DAO s bogatim članovima, no kada se radi o članovima koji možda nemaju dovoljno Ethera za velike pologe, ili kada želite DAO na globalnoj razini (Blockada DAO financira druženja diljem svijeta), ovo nije aplikabilno.

Htjeli smo maknuti čim više prepreka pridruživanju Blockadi pa smo stoga otpornost na Sybil napade _outsourcali_, tj. delegirali vanjskoj "usluzi".

## HumanityDAO

Nedavno je na scenu stupio novi DAO: [HumanityDAO](https://humanitydao.org). Od članova je zahtijevao da tweetaju o svojoj želji za članstvom i prema tome dopustio drugim, postojećim članovima da sude o njihovom "ljudstvu" glasanjem.

Unatoč početnim kontroverzama (neki od prvih članova odlučili su bez razloga spriječiti nove da se pridruže), od tada se HumanityDAO oporavio i trenutno služi kao relativno beskoristan popis više-manje stvarnih ljudi.

Zanemarimo li potencijalne probleme oko privatnosti (nadam se da su svi članovi koristili prazne adrese bez prošlih transakcija prilikom prijave!), HumanityDAO je baš takva vrsta popisa kakva nam treba u Blockada DAO-u.

Umjesto da izmišljamo toplu vodu i kreiramo još jedan popis stvarnih ljudi na vlastiti način, odlučio sam koristiti D2D metodologiju (DAO 2 DAO) tako da će Blockada čitati podatke iz HumanityDAO prije nego novim članovima dopusti da se pridruže. Drugim riječima, da bi netko postao član Blockade mora _biti čovjek_. No, kako to učiniti za vlastiti projekt? 

Dovoljan je jedan modifikator funkcije i dvije-tri linije koda. Puni kod primjera s kojim ćemo raditi slijedi, a objašnjenja su u tekstu ispod.

```solidity
pragma solidity ^0.5.2;

contract HumanityDAO {
    function isHuman(address who) public view returns (bool) {}
}

contract onlyHumanCheck {

    uint256 public counter;
    HumanityDAO dao;

    constructor() public {
        dao = HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90);
    }

    function increaseCounter() public onlyHuman {
        counter = counter + 1;
    }

    modifier onlyHuman() {
        require(dao.isHuman(msg.sender), "Only callable by a human!");
        _;
    }

}
```

## Objašnjenje

Znamo iz iskustva da je Ethereum adresa HumanityDAO ugovora `0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90`. Ako je provjerimo u Etherscanu, primjetiti ćemo da sadrži upravo tu funkciju koja nam treba - `isHuman`, kao i izvorni kod za istu, spreman za kopiranje.

![Etherscan pregled](https://bitfalls.com/wp-content/uploads/2018/10/01-4.png)

![Etherscan kod](https://bitfalls.com/wp-content/uploads/2018/10/02-2.png)

U primjeru gore naš ugovor nazvali smo `onlyHumanCheck`. Drugi ugovor pri vrhu, `HumanityDAO`, nije pravi HumanityDAO već apstraktni dio pravog HumanityDAO-a koji nam je potreban kako bismo mogli pozvati `isHuman` funkciju. Abstraktne funkcije ne moraju imati tijelo, već samo moraju odgovarati _potpisu_ funkcije, tj. moraju imati iste ulazne i izlazne vrijednosti.

Zatim definiramo naš HumanityDAO _stub_ (djelomični) ugovor:

```solidity
contract HumanityDAO {
    function isHuman(address who) public view returns (bool) {}
}
```

Funkcija `isHuman` sada će biti dostupna našem pametnom ugovoru ako u njemu izgradimo pravilnu `HumanityDAO` instancu ugovora. Evo kako to učiniti:

```solidity
    HumanityDAO dao;

    constructor() public {
        dao = HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90);
    }
```

Definiramo novu varijablu zvanu `dao` tipa `HumanityDAO`. To znači "spremiti ćemo HumanityDAO ugovor u ovu varijablu".

Zatim, u konstruktoru našeg ugovora (tj. funkciji koja se sama poziva kada se ugovor kreira na blockchainu) definiramo vrijednost varijable `dao` kao `HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90)`.

To nazivamo novom _instancom_ tj. kopijom `HumanityDAO` ugovora - ne duplikatom, već referencom na original jer se radi o istoj adresi. Bilo koja funkcija koju izvršimo na našoj kopiji izvršava se na originalnom HumanityDAO ugovoru. U ovom slučaju sada imamo mogućnost da pozivamo funkciju koju smo prije definirali (`isHuman`) na `dao` varijabli koja sadrži referencu na željeni ugovor.

_Napomena: kada se koristi neki od Ethereum [testnetova](https://bitfalls.com/hr/2018/05/31/what-is-an-ethereum-testnet-and-how-is-it-used/), adrese su drukčije. U ovom članku sve se odvija na mainnetu._

Zatim gradimo svoj modifikator:

```solidity
    modifier onlyHuman() {
        require(dao.isHuman(msg.sender), "Only callable by a human!");
        _;
    }
```

Modifikatori su uvjeti koji se mogu nadodati na neke postojeće funkcije kako bi im promijenili tok, bez da ugrožavaju DRY (don't repeat yourself - ne ponavljaj se) princip. Prva linija, `require`, zahtijeva da `msg.sender`, tj. pošiljatelj transakcije, vraća `true` iz `isHuman` funkcije na varijabli `dao`. Ako ne vrati `true` znači da nije registriran kao čovjek i emitira se poruka `Only callable by a human` koja objašnjava zašto je došlo do greške. Linija koja sadrži samo `_;` znači "zalijepi ostatak funkcije ovdje". Dakle, modifikatori će zalijepiti kod funkcije koju modificiraju na mjesto te linije. Pogledajmo kako se taj modifikator koristi:

```solidity
    function increaseCounter() public onlyHuman {
        counter = counter + 1;
    }
```

Uz ovu funkciju na mjestu, samo "ljudi" će moći pozvati `increaseCounter` funkciju jer ista ima modifikator `onlyHuman`.

## Testiranje

Najlakši način za isprobati ovo u nekom sučelju je putem OneClickDapp: [https://oneclickdapp.com/origin-smart/](https://oneclickdapp.com/origin-smart/).

Ako pokušate kliknuti na "Sign & Submit" gumb dok u MetaMasku imate aktivni račun koji nije u HumanityDAO, dobiti ćete upozorenje prije nego i uspijete poslati transakciju.

![Impossible execution warning](https://bitfalls.com/wp-content/uploads/2018/10/04-1.png)

Ako pokušate ponovno s adresom koja je "čovjek", sve je u redu:

![Sve je u redu s transakcijom](https://bitfalls.com/wp-content/uploads/2018/10/05-1.png)

## Zaključak

Ethereum je programabilni novac. Možemo ga usporediti s financijskim Lego Technics setovima - komponentama koje možete povezati jednu s drugom i izgraditi zaista zadivljujuće robote. DAO-DAO komunikacija poput ove koja je gore demonstrirana predstavlja evoluciju u automatizaciji upravljanja zajednicama i financijama.

Ako gradite neku aplikaciju na Ethereum blockchainu, svakako vas ohrabrujem da koristite već postojeće tokene i spajate se na postojeće ugovore - koliko god privlačno zvučalo pokrenuti nešto skroz svoje, spajanjem postojećih elemenata dižete vrijednost cijelom ekosustavu. A to je upravo ono što nam svima i najviše koristi.
