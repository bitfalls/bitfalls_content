Last year, hackers stole and leaked an NSA-developed computer exploit which was used to lock down and ransom off computer data. These days the exploit has found a new purpose: [mining][mine] [cryptocurrency][cc].

In April 2017 the [ShadowBrokers][sb] hacker group leaked EternalBlue - a Windows OS exploit. This exploit was turned into a devastating ransomware just a month after its release to the public, when it was dubbed [WannaCry][wc]. WannaCry is a blackmailing tool which encrypts a hard drive and asks the owners for ransom in the form of [Bitcoin][btc] within a week, otherwise it deletes all data on the infected computer.

These days EternalBlue has a new purpose - mining. This worm is called WannaMine and while it may not seem as devastating as WannaCry at first glance, [CrowdStrike][cs] claims companies and institutions are being taken offline for weeks at a time because of the mining locking up their computers with off-the-charts CPU usage.

The number of infected machines keeps growing because it's exceptionally difficult to detect infections. The exploit does not rely on downloading additional software, and the computer is easily infected by opening an email or a web page. WannaMine then uses the Powershell and Windows Management Instrumentation apps to do its dirty work.

WannaMine does not utilize EternalBlue immediately - it first uses [Mimikatz][mimi], a tool which pulls usernames and passwords out of computer memory. If this fails, EternalBlue activates. Should a computer be connected to a larger network and the harvesting of data proves successful, the whole network gets infected.

The cryptocurrency being mined is Monero because it doesn't need expensive hardware and can be mined on a personal computer invisibly. The only way to notice it is noticing the computer slowing down.

[Adyllkuzz][ady] was the first worm which used EternalBlue, but WannaMine is far more sophisticated in that it doesn't download additional tools. By using tools already present on every Windows machine, WannaMine easily remains undetected for long periods of time.

More infections are expected before a good antidote is developed.

---

If you found this article useful or interesting, please [consider donating][donate] to keep our operation running.

[donate]: https://bitfalls.com/donate
[mine]: https://bitfalls.com/glossary/#mining
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[btc]: https://bitfalls.com/2017/09/01/send-receive-bitcoin/
[mimi]: https://www.offensive-security.com/metasploit-unleashed/mimikatz/
[cs]: https://www.crowdstrike.com/blog/cryptomining-harmless-nuisance-disruptive-threat/
[sb]: https://motherboard.vice.com/en_us/topic/the-shadow-brokers
[wc]: https://motherboard.vice.com/en_us/article/4xkqqg/a-massive-ransomware-explosion-is-hitting-targets-all-over-the-world
[ady]: https://www.proofpoint.com/us/threat-insight/post/adylkuzz-cryptocurrency-mining-malware-spreading-for-weeks-via-eternalblue-doublepulsar
