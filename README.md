# TODO

## O com chceme pisat dokument (cca)
* Ponuka
* Povodny stav systemu, nedostatky, poziadavky co fixnut, co pridat
* Pouzite technologie
* Architektura celeho systemu
    * Su nejaki agenti, je nejaky monitor, na agentovi moze byt pripojeny len jeden monitor. Monitor posiela prikazy, agent ich vykona/odpoveda (JSON format). Monitor periodicky updatuje status agentov
      a monitorovane procesy na nich do Mysql databazy.
    * Agent podla nastaveneho filtru posiela pakety na server. Na serveri sa pakety zapisu do HBase databazy. PcapSender ich z HBase vyberie, vytvori .pcap subor, posle do ActiveMQ fronty.
      Bezia nejake detekcne moduly, ktore vyberaju .pcap subory z fronty, vykonavaju na nich detekciu. Detekcia sa zapisuje do Mysql databazy.
* Build agentov
    * Windows - visual studio, boost, npcap atd.
    * Linux - cmake, boost, libpcap atd.
* Build monitoru
    * Windows - visual studio, boost, mysqlconnector
    * Linux - cmake, boost, mysqlconnector
* Popis JSON formatu v akom komunikuju monitor a agent
* Popis novych/zmenenych veci v monitore (https://github.com/feistu-tp-spde3/client-cli)
    * Ake thready bezia
    * Ako sa hladaju agenti (UDP broadcast)
    * Ako sa identifikuje agent
    * XML config
    * Dostupne prikazy v Cmdline (vstup, vystup, co sa deje ked sa to posle)
    * Ako funguje updatovaci thread (kedy sa co updatuje, v akom intervale)
* Popis novych/zmenenych veci v agentovi (https://github.com/feistu-tp-spde3/agent)
    * Ake thready bezia
    * XML config -- vysvetlit kazdy element
    * Sniffer
    * Ako sa posielaju pakety, v akom formate a preco (uz neposielame pakety zo suboru ale z pamate)
    * Ako sa monitoruju procesy (Windows aj Linux)
    * Prikazy od monitoru a ako na nich reaguje agent
    * Ukladanie XML configu pri zmene filtru, monitorovanych procesov apod.
* Zmeny v HBaseWriter
    * Aky format bol pouzity predtym
    * Ako sa to parsuje teraz
    * Nedostatky?
* Detekcie
    * Pripojenie do DB
    * Zmeny proti predoslym
* Databaza
    * Schema tabuliek
    * Vysvetlit tabulky
* Web
    * Ako vyzera
    * Ako funguje
* Performance
* Future work
    * Neposielat pakety ako hexstring, ale binarne
    * Security (SSL/TLS na stranku, sifrovana komunikacia na sieti, certifikaty...)
    * ..
* Zaver
    
- [X] Uvod
- [X] Ponuka
- [X] Povodny stav systemu, nedostatky, poziadavky co fixnut, co pridat
- [X] Architektura systemu
- [X] Pouzite technologie
- [X] Popis komunikacie medzi monitorom a agentom (spracovanie, format)
- [X] Popis novych/zmenenych veci v monitore (WILL NEED REVIEW)
- [X] Popis novych/zmenenych veci v agentovi (WILL NEED REVIEW)
- [X] Zmeny v HBaseWriter
- [X] Detekcie
- [X] Databaza
- [X] Web
- [X] Build agentov
- [X] Build monitoru
- [ ] Performance (???)
- [X] Future work
- [X] Zaver
