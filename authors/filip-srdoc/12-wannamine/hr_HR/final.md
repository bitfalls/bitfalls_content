Hakeri su prošle godine ukrali i objavili način iskorištavanja ranjivosti računala (_exploit_) kojeg je razvila NSA (National Security Agency). Ovih dana _exploit_ je dobio novu namjenu: [rudarenje][mine] [kriptovaluta][cc].

U travnju 2017. godine hakerska grupa [Shadow Brokers][sb] pustila je u javnost EternalBlue, _exploit_ za Windowse, koji je nakon samo mjesec dana pretvoren u razarajući ransomware zvan [WannaCry][wc]. WannaCry ransomware je ucjenjivački malware koji je u masivnom cyber napadu zarazio oko 230 tisuća računala diljem svijeta zaključavajući hard diskove zaraženih računala.  Za otključavanje svojih računala svjetski poznate korporacije, bolnice i ministarstva morali platiti određenu svotu u [bitcoinu][btc] u roku tjedan dana, u protivnom bi svi podaci bili izbrisani.

Danas je _exploit_ EternalBlue  dobio novu namjenu, "otmicu" računala u svrhu rudarenja kriptovaluta.  Ovaj crv (_worm_) nazvan je WannaMine i možda se nekima ne čini tako opasan kao WannaCry koji je zaključavao računala, ali [CrowdStrike][cs] kaže kako zbog WannaMine-a kompanije nisu u mogućnosti raditi danima i tjednima jer WannaMine iskorištava ogromnu snagu procesora kako bi rudarenje bilo izvedivo.

Sve je veći broj zaraženih računala, a dodatan problem stvara teško otkrivanje ovog _worma_ jer WannaMine ne skida nikakve dodatne aplikacije na zaraženo računalo. Računalo se lako zarazi otvaranjem zaraženog e-maila ili internet stranice. Nakon toga WannaMine koristi dvije standardne Windows aplikacije, PowerShell i Windows Managment Instrumentation, kako bi one obavile prljav posao.

Međutim, WannaMine ne iskorištava EternalBlue _exploit_ odmah. Prvo koristi [Mimikatz][mimi], alat koji iz memorije računala izvlači  korisnička imena i lozinke. Ukoliko to slučajno ne uspije, u igru ulazi EternalBlue. Ako je zaraženo računalo dio mreže kao što je to slučaj u uredima kompanija, WannaMine će zaraziti sva računala na mreži.

Kriptovaluta koja se u ovom slučaju rudari je Monero. Monero ne zahtjeva skupu opremu za rudarenje već mu je dovoljna snaga osobnog računala da potajno rudari u pozadini pa tako većina ljudi neće ni uvidjeti da im nešto nije u redu s računalom osim što će računalo biti sporije.

[Adyllkuzz][ady] je bio prvi _worm_ koji koristio EternalBlue, no WannaMine je daleko sofisticiraniji jer za razliku od Adyllkuzza ne skida nikakve dodatne aplikacije na računalo već koristi alate koji je ionako moguće naći na svim Windows računalima. Tako je antivirusnim programima teže detektirati i blokirati _worm_ koji ne ostavlja nikakav trag na disku računala. 

Očekuje se sve više zaraženih računala, a na korisnicima je žele li platiti otkupninu ili ne. Sve dok ne plate WannaMine će rudariti kriptovalute na zaraženim računalima i ostvarivati profit.

[mine]: https://bitfalls.com/hr/glossary/#mining
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[btc]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/
[mimi]: https://www.offensive-security.com/metasploit-unleashed/mimikatz/
[cs]: https://www.crowdstrike.com/blog/cryptomining-harmless-nuisance-disruptive-threat/
[sb]: https://motherboard.vice.com/en_us/topic/the-shadow-brokers
[wc]: https://motherboard.vice.com/en_us/article/4xkqqg/a-massive-ransomware-explosion-is-hitting-targets-all-over-the-world
[ady]: https://www.proofpoint.com/us/threat-insight/post/adylkuzz-cryptocurrency-mining-malware-spreading-for-weeks-via-eternalblue-doublepulsar
